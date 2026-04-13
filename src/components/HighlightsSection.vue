<template>
  <section class="section audience-outcomes">
    <div class="container split-grid">
      <article class="soft-card soft-card--audience hover-lift">
        <div class="card-heading">
          <span class="mini-icon mini-icon--blue">
            <img :src="audience.icon" alt="" />
          </span>
          <h3>{{ audience.title }}</h3>
        </div>

        <ul class="list-blocks">
          <li v-for="item in audience.items" :key="item.title">
            <span
              class="audience-check"
              :class="`audience-check--${item.tone}`"
              aria-hidden="true"
            ></span>
            <div>
              <strong>{{ item.title }}</strong>
              <p>{{ item.description }}</p>
            </div>
          </li>
        </ul>
      </article>
      
      <article class="result-card hover-lift">
        <div class="card-heading card-heading--light">
          <span class="mini-icon mini-icon--light">
            <img :src="outcomes.icon" alt="" />
          </span>
          <h3>{{ outcomes.title }}</h3>
        </div>

        <ul class="result-list">
          <li v-for="item in outcomes.items" :key="item">
            <span class="result-list__icon-wrap" aria-hidden="true">
              <img src="/assets/icon/star.svg" alt="" class="result-list__icon" />
            </span>
            <span>{{ item }}</span>
          </li>
        </ul>
      </article>
    </div>
  </section>
</template>

<script setup>
defineProps({
  audience: { type: Object, required: true },
  outcomes: { type: Object, required: true },
})
</script>
