<template>
  <section class="section curriculum-section">
    <div class="container section-wrap">
      <SectionTitle
        :icon="curriculum.icon"
        :title="curriculum.title"
        :description="curriculum.description"
      />

      <div class="mobile-carousel-controls">
        <button type="button" class="carousel-arrow" @click="scrollByCard(-1)">
          <img src="/assets/icon/prev-arrow.svg" alt="上一張" />
        </button>
        <button type="button" class="carousel-arrow" @click="scrollByCard(1)">
          <img src="/assets/icon/next-arrow.svg" alt="下一張" />
        </button>
      </div>

      <div ref="trackRef" class="session-grid session-grid--mobile-scroll">
        <SessionCard
          v-for="item in curriculum.items"
          :key="item.session"
          :session="item.session"
          :title="item.title"
          :points="item.points"
          :tone="item.tone"
        />
      </div>

      <div
        class="mobile-active-indicator"
        :class="`mobile-active-indicator--${currentTone}`"
        aria-hidden="true"
      ></div>
    </div>
  </section>
</template>

<script setup>
import { computed, nextTick, onBeforeUnmount, onMounted, ref } from 'vue'
import SectionTitle from './SectionTitle.vue'
import SessionCard from './SessionCard.vue'

const props = defineProps({
  curriculum: { type: Object, required: true },
})

const trackRef = ref(null)
const currentIndex = ref(0)

const currentTone = computed(() => {
  return props.curriculum.items[currentIndex.value]?.tone || 'blue'
})

function updateCurrentIndex() {
  if (!trackRef.value) return

  const cards = Array.from(trackRef.value.children)
  if (!cards.length) return

  const scrollLeft = trackRef.value.scrollLeft

  let nearestIndex = 0
  let nearestDistance = Infinity

  cards.forEach((card, index) => {
    const distance = Math.abs(card.offsetLeft - scrollLeft)
    if (distance < nearestDistance) {
      nearestDistance = distance
      nearestIndex = index
    }
  })

  currentIndex.value = nearestIndex
}

function scrollByCard(direction) {
  if (!trackRef.value) return
  const amount = Math.round(trackRef.value.clientWidth * 0.86)
  trackRef.value.scrollBy({ left: direction * amount, behavior: 'smooth' })

  window.setTimeout(updateCurrentIndex, 260)
}

function handleScroll() {
  updateCurrentIndex()
}

onMounted(async () => {
  await nextTick()
  updateCurrentIndex()
  trackRef.value?.addEventListener('scroll', handleScroll, { passive: true })
})

onBeforeUnmount(() => {
  trackRef.value?.removeEventListener('scroll', handleScroll)
})
</script>