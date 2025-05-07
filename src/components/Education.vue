<template>
  <h2 class="item__title">{{ title }}</h2>
  <ul class="timeline">
    <li class="timeline__item" v-for="education in educationList" :key="education.id">
      <div class="timeline__wrap">
        <h3 class="timeline__title">{{ education.title }}</h3>
        <p class="timeline__organization">{{ education.institution }}</p>
        <p class="timeline__period">{{ education.period }}</p>
        <p class="timeline__description">{{ education.description }}</p>
      </div>
    </li>
  </ul>
</template>

<script setup>
import { ref } from 'vue';
import educationData from '../data/education.js';

const title = ref('Education');
const educationList = ref(educationData);
</script>

<style scoped>
.timeline {
  margin: 0;
  padding: 0;
  list-style: none;
  position: relative;
}

.timeline::before {
  content: '';
  position: absolute;
  left: -45px;
  top: 10px;
  height: calc(100% - 20px);
  width: 2px;
  background-color: var(--color-border, #E2E6EE);
}

.timeline__item {
  position: relative;
  margin-bottom: 25px;
}

.timeline__item:last-child {
  margin-bottom: 0;
}

.timeline__item::before {
  content: '';
  position: absolute;
  left: -50px;
  top: 10px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: var(--color-primary, #516CF7);
}

.timeline__wrap {
  background-color: var(--color-bg-light, #F7F9FC);
  padding: 20px;
  border-radius: 8px;
  transition: var(--transition-normal, all 0.3s ease);
}

.timeline__wrap:hover {
  transform: translateY(-3px);
  box-shadow: var(--box-shadow, 0 2px 8px rgba(0, 0, 0, 0.1));
}

.timeline__title {
  margin-top: 0;
  margin-bottom: 5px;
  font-family: var(--font-heading, 'Outfit'), sans-serif;
  font-size: var(--font-size-md, 16px);
  color: var(--color-text-dark, #2E2E48);
}

.timeline__organization {
  margin-top: 0;
  margin-bottom: 5px;
  font-family: var(--font-body, 'DM Sans'), sans-serif;
  font-weight: 600;
  font-size: var(--font-size-sm, 14px);
  color: var(--color-primary, #516CF7);
}

.timeline__period {
  margin-top: 0;
  margin-bottom: 10px;
  font-family: var(--font-body, 'DM Sans'), sans-serif;
  font-size: var(--font-size-xs, 12px);
  color: var(--color-text-light, #47516B);
}

.timeline__description {
  margin-top: 0;
  margin-bottom: 0;
  font-family: var(--font-body, 'DM Sans'), sans-serif;
  font-size: var(--font-size-sm, 14px);
  line-height: 1.4;
  color: var(--color-text-light, #47516B);
}
</style>