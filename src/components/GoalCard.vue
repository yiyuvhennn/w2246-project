<template>
  <article class="goal-card hover-lift" :class="`goal-card--${tone}`">
    <span class="goal-card__icon">
      <img :src="icon" alt="" />
    </span>
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
  </article>
</template>

<script setup>
defineProps({
  icon: { type: String, required: true },
  title: { type: String, required: true },
  description: { type: String, required: true },
  tone: { type: String, default: 'blue' },
})
</script>
