<script setup>
import { ref, onMounted } from 'vue';
import Aside from './components/Aside.vue';
import Projects from './components/Projects.vue';
import Education from './components/Education.vue';
import Tools from './components/Tools.vue';


const isPageLoaded = ref(false);

onMounted(() => {
  setTimeout(() => {
    isPageLoaded.value = true;
  }, 100);
});
</script>

<template>
  <main :class="{ 'loaded': isPageLoaded }">
    <div class="aside">
      <Aside />
      
    </div>
    <div class="info">
      <div class="item">
        <Tools />
      </div>
      <div class="item">
        <Projects />
      </div>

    </div>
  </main>
</template>

<style scoped>
.item{
  margin-bottom: var(--space-lg, 24px);
}

main{
  display: grid;
  grid-template-columns: 25% 75%;
  overflow: hidden;
  opacity: 0;
  transform: translateY(10px);
  transition: var(--transition-normal, all 0.3s ease);
}

main.loaded {
  opacity: 1;
  transform: translateY(0);
}

@media (max-width: 870px) {
  main {
    display: block;
  }
}

.aside{
  padding: var(--space-xl, 32px);
  background-color: var(--color-bg-light, #F7F9FC);
}

@media (max-width: 1025px) {
  .aside {
    padding: var(--space-lg, 24px);
  }
}

@media (max-width: 870px) {
  .aside {
    display: grid;
    column-gap: var(--space-lg, 24px);
    grid-template-columns: 1fr 1fr;
  }
}

@media (max-width: 767px) {
  .aside {
    display: block;
  }
}

.info{
  padding: var(--space-xl, 32px) var(--space-lg, 24px) var(--space-xl, 32px) var(--space-lg, 24px);
}

@media (max-width: 767px) {
  .info {
    padding: var(--space-xl, 32px) var(--space-lg, 24px);
  }
}

.item{
  position: relative;
  padding-left: 80px;
}

@media (max-width: 993px) {
  .item {
    padding-left: 50px;
  }
}

@media (max-width: 767px) {
  .item {
    padding-left: var(--space-lg, 24px);
  }
}
</style>