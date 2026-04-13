<template>
  <section class="section teacher-section">
    <div class="container section-wrap">
      <SectionTitle :icon="teacher.sectionIcon" :title="teacher.sectionTitle" />

      <article class="teacher-card hover-lift">
        <div class="teacher-card__top">
          <div class="teacher-card__photo-wrap">
            <img :src="teacher.image" :alt="`${teacher.name} 講師照片`" class="teacher-card__photo" />
            <span class="teacher-card__photo-badge">
              <img src="/assets/icon/badge.svg" alt="" />
            </span>
          </div>

          <div class="teacher-card__content">
            <div class="teacher-card__identity">
              <h3 class="teacher-card__title">{{ teacher.name }}</h3>
              <span class="teacher-card__name">
                <span class="teacher-card__name-icon" aria-hidden="true"></span>
                <span class="teacher-card__name-text">{{ teacher.badge }}</span>
              </span>
            </div>
            <p class="teacher-card__intro">{{ teacher.intro }}</p>
          </div>
        </div>

        <div class="teacher-card__lists">
          <article class="info-list-card info-list-card--blue">
            <h3>{{ teacher.experience.title }}</h3>
            <ul>
              <li v-for="item in teacher.experience.items" :key="item">{{ item }}</li>
            </ul>
          </article>

          <article class="info-list-card info-list-card--purple">
            <h3>{{ teacher.teaching.title }}</h3>
            <ul>
              <li v-for="item in teacher.teaching.items" :key="item">{{ item }}</li>
            </ul>
          </article>
        </div>
      </article>
    </div>
  </section>
</template>

<script setup>
import SectionTitle from './SectionTitle.vue'

defineProps({
  teacher: { type: Object, required: true },
})
</script>
