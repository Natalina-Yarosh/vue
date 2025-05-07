<template>
  <h2 class="item__title">{{ title }}</h2>
  
  <div class="tech-filters" v-if="uniqueTechnologies.length > 1">
    <button 
      v-for="tech in ['all', ...uniqueTechnologies]" 
      :key="tech"
      :class="{ active: selectedTech === tech }"
      @click="setTechFilter(tech)"
    >
      {{ tech }}
    </button>
  </div>
  
  <ul class="projects">
    <li class="project" v-for="project in filteredProjects" :key="project.id">
      <div class="project__wrap-img">
        <img :src="project.image" :alt="`Скриншот проекта ${project.name}`">
      </div>
      <div class="project__wrap-info">
        <h3 class="project__name">{{ project.name }}</h3>
        
        <div class="project__technologies" v-if="project.technologies && project.technologies.length">
          <span v-for="tech in project.technologies" :key="tech" class="tech-tag">
            {{ tech }}
          </span>
        </div>
        
        <p class="project__description">{{ project.description }}</p>
      </div>
      <div class="project__wrap-link">
        <a class="project__link" :href="project.linkPath" target="_blank" rel="noopener noreferrer">
          <div class="project__svg">
            <svg width="8" height="8" viewBox="0 0 8 8" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M2.89532 6.48385C2.26339 6.48385 1.69369 6.10319 1.45182 5.51939C1.20995 4.93558 1.34355 4.26356 1.79032 3.81666L2.45344 3.15353L2.89532 3.59541L2.23251 4.25822C1.99565 4.49508 1.90315 4.8403 1.98984 5.16385C2.07654 5.4874 2.32926 5.74013 2.65281 5.82682C2.97636 5.91352 3.32159 5.82101 3.55844 5.58416L4.22126 4.92134L4.66313 5.36353L4.00032 6.02635C3.70784 6.32026 3.30996 6.48499 2.89532 6.48385ZM3.11626 5.14228L2.67438 4.70041L4.88407 2.49072L5.32594 2.93259L3.11657 5.14197L3.11626 5.14228ZM5.54719 4.47947L5.10501 4.03759L5.76782 3.37478C6.0079 3.13864 6.10288 2.79186 6.01664 2.46634C5.93041 2.14081 5.6762 1.88655 5.3507 1.80023C5.02519 1.71392 4.6784 1.80882 4.44219 2.04884L3.77907 2.71166L3.33719 2.26978L4.00032 1.60666C4.61128 1.00102 5.59687 1.00318 6.20518 1.61148C6.81348 2.21979 6.81564 3.20538 6.21001 3.81634L5.54719 4.47916V4.47947Z" fill="#516CF7"/>
            </svg>
          </div>
          {{ project.linkName }}
        </a>
      </div>
    </li>
  </ul>
</template>

<script setup>
import { ref, computed } from 'vue';
import projectsData from '../data/projects.js';

const title = ref('Последние проекты');
const projects = ref(projectsData);
const selectedTech = ref('all');

const uniqueTechnologies = computed(() => {
 
  const techs = new Set();
  projects.value.forEach(project => {
    if (project.technologies && Array.isArray(project.technologies)) {
      project.technologies.forEach(tech => techs.add(tech));
    }
  });
  return [...techs].sort();
});

const filteredProjects = computed(() => {
  if (selectedTech.value === 'all') return projects.value;
  return projects.value.filter(project => 
    project.technologies && project.technologies.includes(selectedTech.value)
  );
});

const setTechFilter = (tech) => {
  selectedTech.value = tech;
};
</script>

<style scoped>

.projects{
  margin-top: 24px;
  display: flex;
  flex-wrap: wrap;
  gap: 30px 20px;
}

.project{
  width: 49%;
}

.project__wrap-img{
  margin-bottom: 15px;
}

.project__wrap-img img{
  width: 100%;
  height: auto;
  transition: transform 0.3s;
  border-radius: 4px;
}

.project__wrap-img {
  overflow: hidden;
}

.project:hover .project__wrap-img img {
  transform: scale(1.05);
}

.project__name{
  margin-bottom: 5px;
  font-family: 'Outfit', sans-serif;
  font-size: 16px;
  line-height: 1.16;
  color: var(--color-text-dark, #2E2E48);
}

.project__description{
  margin-top: 0;
  margin-bottom: 15px;
  font-family: 'DM Sans', sans-serif;
  font-size: 14px;
  line-height: 1.4;
  color: var(--color-text-light, #47516B);
}

.project__wrap-link a{
  display: flex;
  align-items: center;
  gap: 5px;
  text-decoration: none;
  font-family: 'DM Sans', sans-serif;
  font-weight: 600;
  font-size: 14px;
  color: var(--color-primary, #516CF7);
}

@media (max-width: 767px){
  .project{
    width: 100%;
  }
}


.tech-filters {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
  flex-wrap: wrap;
}

.tech-filters button {
  background: var(--color-bg-light, #F7F9FC);
  border: 1px solid var(--color-primary, #516CF7);
  color: var(--color-text-dark, #2E2E48);
  padding: 6px 12px;
  border-radius: 20px;
  cursor: pointer;
  font-size: 14px;
  transition: all 0.3s;
}

.tech-filters button.active, 
.tech-filters button:hover {
  background: var(--color-primary, #516CF7);
  color: white;
}

.project__technologies {
  display: flex;
  gap: 6px;
  flex-wrap: wrap;
  margin-bottom: 10px;
}

.tech-tag {
  background: var(--color-bg-light, #F7F9FC);
  color: var(--color-primary, #516CF7);
  font-size: 12px;
  padding: 3px 8px;
  border-radius: 12px;
  font-weight: 500;
}
</style>