<template>
  <h2 class="item__title">{{ title }}</h2>
  <ul class="achievements">
    <li class="achievement" v-for="achievement in achievementsList" :key="achievement.id">
      <div class="achievement__wrap">
        <div class="achievement__header">
          <h3 class="achievement__title">{{ achievement.title }}</h3>
          <p class="achievement__year">{{ achievement.year }}</p>
        </div>
        <p class="achievement__organization">{{ achievement.organization }}</p>
        <p class="achievement__description">{{ achievement.description }}</p>
      </div>
    </li>
  </ul>
</template>

<script setup>
import { ref } from 'vue';
import achievementsData from '../data/achievements.js';

const title = ref('Achievements');
const achievementsList = ref(achievementsData);
</script>

<style scoped>
.achievements {
  margin: 0;
  padding: 0;
  list-style: none;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
  margin-top: 20px;
}

.achievement__wrap {
  background-color: var(--color-bg-light, #F7F9FC);
  padding: 20px;
  border-radius: 8px;
  height: 100%;
  border-left: 3px solid var(--color-primary, #516CF7);
  transition: var(--transition-normal, all 0.3s ease);
}

.achievement__wrap:hover {
  transform: translateY(-3px);
  box-shadow: var(--box-shadow, 0 2px 8px rgba(0, 0, 0, 0.1));
}

.achievement__header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 5px;
}

.achievement__title {
  margin: 0;
  font-family: var(--font-heading, 'Outfit'), sans-serif;
  font-size: var(--font-size-md, 16px);
  color: var(--color-text-dark, #2E2E48);
}

.achievement__year {
  margin: 0;
  font-family: var(--font-body, 'DM Sans'), sans-serif;
  font-weight: 600;
  font-size: var(--font-size-xs, 12px);
  color: var(--color-primary, #516CF7);
  background-color: rgba(81, 108, 247, 0.1);
  padding: 3px 8px;
  border-radius: 12px;
}

.achievement__organization {
  margin-top: 0;
  margin-bottom: 10px;
  font-family: var(--font-body, 'DM Sans'), sans-serif;
  font-weight: 500;
  font-size: var(--font-size-sm, 14px);
  color: var(--color-text-dark, #2E2E48);
}

.achievement__description {
  margin-top: 0;
  margin-bottom: 0;
  font-family: var(--font-body, 'DM Sans'), sans-serif;
  font-size: var(--font-size-sm, 14px);
  line-height: 1.4;
  color: var(--color-text-light, #47516B);
}

@media (max-width: 767px) {
  .achievements {
    grid-template-columns: 1fr;
  }
}
</style>