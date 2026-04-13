<template>
  <article class="session-card hover-lift" :class="`session-card--${tone}`">
    <span class="session-chip" translate="no">{{ session }}</span>
    <h3>{{ title }}</h3>
    <ul>
      <li v-for="point in points" :key="point">{{ point }}</li>
    </ul>
  </article>
</template>

<script setup>
defineProps({
  session: { type: String, required: true },
  title: { type: String, required: true },
  points: { type: Array, required: true },
  tone: { type: String, default: 'blue' },
})
</script>