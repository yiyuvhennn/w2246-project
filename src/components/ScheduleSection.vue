<template>
  <section class="section curriculum-section">
    <div class="container section-wrap">
      <SectionTitle :icon="curriculum.icon" :title="curriculum.title" :description="curriculum.description" />

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
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import SectionTitle from './SectionTitle.vue'
import SessionCard from './SessionCard.vue'

defineProps({
  curriculum: { type: Object, required: true },
})

const trackRef = ref(null)

function scrollByCard(direction) {
  if (!trackRef.value) return
  const amount = Math.round(trackRef.value.clientWidth * 0.86)
  trackRef.value.scrollBy({ left: direction * amount, behavior: 'smooth' })
}
</script>
