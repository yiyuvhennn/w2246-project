<template>
  <section class="section goals-section">
    <div class="container section-wrap">
      <SectionTitle :icon="goals.icon" :title="goals.title" :description="goals.description" />

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
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import SectionTitle from './SectionTitle.vue'
import GoalCard from './GoalCard.vue'

defineProps({
  goals: { type: Object, required: true },
})

const trackRef = ref(null)

function scrollByCard(direction) {
  if (!trackRef.value) return
  const amount = Math.round(trackRef.value.clientWidth * 0.82)
  trackRef.value.scrollBy({ left: direction * amount, behavior: 'smooth' })
}
</script>
