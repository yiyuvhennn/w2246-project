<template>
  <div class="page-shell">
    <main>
      <HeroSection :hero="eventData.hero" :quick-points="eventData.quickPoints" />
      <HighlightsSection :audience="eventData.audience" :outcomes="eventData.outcomes" />
      <GoalsSection :goals="eventData.goals" />
      <TeacherSection :teacher="eventData.teacher" />
      <ScheduleSection :curriculum="eventData.curriculum" />
      <CtaSection :cta="eventData.cta" />
    </main>
  </div>
</template>

<script setup>
import { eventData } from './data/eventData'
import HeroSection from './components/HeroSection.vue'
import HighlightsSection from './components/HighlightsSection.vue'
import GoalsSection from './components/GoalsSection.vue'
import TeacherSection from './components/TeacherSection.vue'
import ScheduleSection from './components/ScheduleSection.vue'
import CtaSection from './components/CtaSection.vue'
</script>
