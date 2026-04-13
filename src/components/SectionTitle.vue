<template>
  <div class="section-title" :class="{ center: centered }">
    <span v-if="icon" class="section-title__icon">
      <img :src="icon" alt="" />
    </span>
    <div class="section-title__copy">
      <h2>{{ title }}</h2>
    </div>
    <p v-if="description">{{ description }}</p>
  </div>
</template>

<script setup>
defineProps({
  title: { type: String, required: true },
  description: { type: String, default: '' },
  icon: { type: String, default: '' },
  centered: { type: Boolean, default: true },
})
</script>
