<template>
  <section class="section goals-section">
    <div class="container section-wrap">
      <SectionTitle
        :icon="goals.icon"
        :title="goals.title"
        :description="goals.description"
      />

      <div class="mobile-carousel-controls">
        <button type="button" class="carousel-arrow" @click="scrollByCard(-1)">
          <img src="/assets/icon/prev-arrow.svg" alt="上一張" />
        </button>
        <button type="button" class="carousel-arrow" @click="scrollByCard(1)">
          <img src="/assets/icon/next-arrow.svg" alt="下一張" />
        </button>
      </div>

      <div ref="trackRef" class="goal-grid goal-grid--mobile-scroll">
        <GoalCard
          v-for="goal in goals.items"
          :key="goal.title"
          :icon="goal.icon"
          :title="goal.title"
          :description="goal.description"
          :tone="goal.tone"
        />
      </div>

      <div
        class="mobile-dots"
        :style="{ '--active-index': currentIndex }"
        aria-hidden="true"
      >
        <div class="mobile-dots__track">
          <span
            v-for="goal in goals.items"
            :key="`${goal.title}-dot`"
            class="mobile-dots__slot"
          >
            <span class="mobile-dots__dot"></span>
          </span>

          <span
            class="mobile-dots__active"
            :class="`mobile-dots__active--${currentTone}`"
          ></span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { computed, nextTick, onBeforeUnmount, onMounted, ref } from 'vue'
import SectionTitle from './SectionTitle.vue'
import GoalCard from './GoalCard.vue'

const props = defineProps({
  goals: { type: Object, required: true },
})

const trackRef = ref(null)
const currentIndex = ref(0)
let rafId = 0

const currentTone = computed(() => {
  return props.goals.items[currentIndex.value]?.tone || 'blue'
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

function handleScroll() {
  cancelAnimationFrame(rafId)
  rafId = requestAnimationFrame(updateCurrentIndex)
}

function scrollByCard(direction) {
  if (!trackRef.value) return

  const firstCard = trackRef.value.querySelector('.goal-card')
  const amount = firstCard
    ? firstCard.clientWidth + 14
    : Math.round(trackRef.value.clientWidth * 0.88)

  trackRef.value.scrollBy({
    left: direction * amount,
    behavior: 'smooth',
  })

  window.setTimeout(updateCurrentIndex, 280)
}

onMounted(async () => {
  await nextTick()
  updateCurrentIndex()
  trackRef.value?.addEventListener('scroll', handleScroll, { passive: true })
})

onBeforeUnmount(() => {
  cancelAnimationFrame(rafId)
  trackRef.value?.removeEventListener('scroll', handleScroll)
})
</script>