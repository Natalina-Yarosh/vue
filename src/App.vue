<script setup>
import Aside from './components/Aside.vue';
import Education from './components/Education.vue';
import Achievements from './components/Achievements.vue';
import Tools from './components/Tools.vue';
import Projects from './components/Projects.vue';
import Certificates from './components/Certificates.vue';
</script>

<template>
  <main>
    <div class="aside">
      <Aside />
    </div>
    <div class="info">
       <Education />
       <Achievements />
       <Tools />
       <Projects />
       <Certificates />
    </div>
  </main>
</template>

<style scoped>

main{
  display: grid;
  grid-template-columns: 25% 75%;
  overflow: hidden;

  @media (max-width:870px) {
    display: block;
  }
}

.aside{
  padding: 40px;
  background-color: #F7F9FC;

  @media (max-width:1025px) {
    padding: 20px;
  }

  @media (max-width:870px) {
    display: grid;
    column-gap: 20px;
    grid-template-columns: 1fr 1fr;
  }

  @media (max-width:767px) {
    display: block;
  }
}

.info{
  padding: 32px 24px 32px 20px;

  @media (max-width:767px) {
    padding: 32px 20px;
  }
}

.item{
  position: relative;
  padding-left: 80px;

  @media (max-width:993px) {
    padding-left: 50px;
  }

  @media (max-width:767px){
    padding-left: 20px;
  }
}

.item::before{
  content: '';
  position: absolute;
  left: 30px;
  top: 0;
  height: 150%;
  display: block;
  width: 0.5px;
  background-color: #E2E6EE;
}

.item::after{
  content: '';
  position: absolute;
  left: 30px;
  top: -5px;
  transform: translateX(-50%);
  height: 30px;
  width: 30px;
  display: block;

  background-repeat: no-repeat;
  background-size: auto;
  background-position: 50% 40%;
  background-image: url(./assets/icon.svg);
}

@media (max-width:993px) {
  .item::before,
  .item::after{
    left: 15px;
  }
}

@media (max-width:767px) {
  .item::before,
  .item::after{
    left: 0;
  }
}
</style>
