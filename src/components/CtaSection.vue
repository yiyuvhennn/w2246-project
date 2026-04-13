<template>
  <section class="section cta-section">
    <div class="container">
      <article class="cta-banner">
        <div class="cta-banner__content">
          <div class="cta-banner__icon" aria-hidden="true">
            <span
              class="cta-banner__icon-shape"
              :style="{ '--icon-url': `url(${cta.icon})` }"
            ></span>
          </div>
          <h2>
            <span>{{ cta.titleLine1 }}</span>
            <span>{{ cta.titleLine2 }}</span>
          </h2>
          <p>
            這門課，帶你從
            <span class="cta-highlight cta-highlight--blue">{{ cta.highlights[0] }}</span>
            →
            <span class="cta-highlight cta-highlight--purple">{{ cta.highlights[1] }}</span>
            →
            <span class="cta-highlight cta-highlight--pink">{{ cta.highlights[2] }}</span>
          </p>
        </div>
      </article>
    </div>
  </section>
</template>

<script setup>
defineProps({
  cta: { type: Object, required: true },
})
</script>
