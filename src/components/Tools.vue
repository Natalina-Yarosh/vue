<template>
  <h2 class="item__title">{{ title }}</h2>
  
  <div class="skills-container" v-for="category in toolsCategories" :key="category.id">
    <h3 class="skills-category">{{ category.category }}</h3>
    
    <div class="skills">
      <div class="skill" v-for="(skill, index) in category.skills" :key="index">
        <div class="skill__header">
          <span class="skill__name">{{ skill.name }}</span>
          <span class="skill__level">{{ skill.level }}%</span>
        </div>
        <div class="skill__bar">
          <div class="skill__progress" :style="{ width: `${skill.level}%` }"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import toolsData from '../data/tools.js';

const title = ref('Skills & Tools');
const toolsCategories = ref(toolsData);


onMounted(() => {
  const progressBars = document.querySelectorAll('.skill__progress');
  
 
  progressBars.forEach(bar => {
    bar.style.transition = 'none';
    bar.style.width = '0%';
  });
  
  
  setTimeout(() => {
    progressBars.forEach(bar => {
      bar.style.transition = 'width 1s ease-in-out';
      bar.style.width = bar.getAttribute('style').split(':')[1];
    });
  }, 300);
});
</script>

<style scoped>
.skills-container {
  margin-bottom: 30px;
}

.skills-container:last-child {
  margin-bottom: 0;
}

.skills-category {
  margin-top: 0;
  margin-bottom: 15px;
  font-family: var(--font-heading, 'Outfit'), sans-serif;
  font-size: var(--font-size-md, 16px);
  color: var(--color-text-dark, #2E2E48);
}

.skills {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 15px;
}

.skill {
  margin-bottom: 10px;
}

.skill__header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 5px;
}

.skill__name {
  font-family: var(--font-body, 'DM Sans'), sans-serif;
  font-weight: 500;
  font-size: var(--font-size-sm, 14px);
  color: var(--color-text-dark, #2E2E48);
}

.skill__level {
  font-family: var(--font-body, 'DM Sans'), sans-serif;
  font-size: var(--font-size-xs, 12px);
  color: var(--color-text-light, #47516B);
}

.skill__bar {
  height: 6px;
  width: 100%;
  background-color: var(--color-bg-light, #F7F9FC);
  border-radius: 3px;
  overflow: hidden;
}

.skill__progress {
  height: 100%;
  background-color: var(--color-primary, #516CF7);
  border-radius: 3px;
  width: 0%; /* Начальное значение для анимации */
}

@media (max-width: 767px) {
  .skills {
    grid-template-columns: 1fr;
  }
}
</style>