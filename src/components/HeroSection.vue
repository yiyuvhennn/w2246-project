<template>
  <section class="hero section">
    <div class="container hero__inner">
      <div class="hero__decor hero__decor--left-shape"></div>
      <!-- <div class="hero__decor hero__decor--left-lines"></div> -->
      <!-- <div class="hero__decor hero__decor--right-ring"></div> -->
      <div class="hero__decor hero__decor--right-shape"></div>

      <div class="hero__badge">
        <span class="hero__badge-icon" aria-hidden="true"></span>
        <span>{{ hero.badge }}</span>
      </div>

      <h1>{{ hero.title }}</h1>
      <p class="hero__description">{{ hero.description }}</p>

      <div class="hero__pills">
        <div
          v-for="point in quickPoints"
          :key="point.text"
          :class="['hero-pill', 'hover-lift', point.className]"
        >
          <span
            class="hero-pill__icon"
            :style="{ '--icon-url': `url(${point.icon})` }"
            aria-hidden="true"
          ></span>
          <span class="hero-pill__text">{{ point.text }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
defineProps({
  hero: { type: Object, required: true },
  quickPoints: { type: Array, required: true },
})
</script>
