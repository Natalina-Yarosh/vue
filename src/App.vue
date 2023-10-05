<script setup>
import Aside from './components/Aside.vue'
import Info from './components/Info.vue'
</script>

<template>
  <div>
    <Aside  :user-name="userName"  :user-main-info="userMainInfo"/>
    <div>
       <Info msg="Vite + Vue" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userName: 'Nataliya Yarosh',
      userMainInfo: 'A well-organized, creative and goaloriented graduate possessing excellent communication, problem-solving and leadership skills with a flair to explore Computer Science Engineering',
      
    };
  },
};

</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
