<template>
  <div class="main-info divider">
    <div class="main-info__wrap-img">
      <img class="main-info__img" :src='userInfo.image' :alt="`Фото ${userInfo.name}`">
    </div>
    <h1 class="main-info__title">{{ userInfo.name }}</h1>
    <p class="main-info__text">{{ userInfo.mainInfo }}</p>
  </div>

  <ul class="info divider">
    <li class="info__item" v-for="info in contactInfo" :key='info.id'>
      <div class="info__wrap-img">
        <img :src="info.icon" :alt="info.name">
      </div>
      <div class="info__wrap-text">
        <p class="info__text">{{ info.name }}</p>
        <div :class="[ {underline: info.isUnderline}, 'info__link' ]" v-html="info.link"></div>
      </div>
    </li>
  </ul>

  <div class="socials divider"> 
    <p class="info__title">Socials</p>
    <ul class="info">
      <li class="info__item" v-for="social in socialLinks" :key='social.id'>
        <div :class="[social.id, 'info__wrap-img']">
          <img :src="social.icon" :alt="social.name">
        </div>
        <div class="info__wrap-text">
          <p class="info__text">{{ social.name }}</p>
          <div class="info__link" v-html="social.link"></div>
        </div>
      </li>
    </ul>
  </div>

  <div class="languages divider">
    <p class="info__title">Languages</p>
    <ul class="info">
      <li class="info__item" v-for="language in languagesList" :key="language.id">
        <div class="info__wrap-img">
          <img :src="language.icon" :alt="language.name">
        </div>
        <div class="info__wrap-text">
          <p class="info__text">{{ language.name }}</p>
          <p class="info__link">{{ language.info }}</p>
        </div>
      </li>
    </ul>
  </div>

  <div class="personal-details">
    <p class="info__title">Personal Details</p>
    <ul class="info"> 
      <li class="info__details-item" v-for="(detail, name) in personalDetails" :key="name">
        <span class="info__details-name">{{name}}:</span> {{detail}}
      </li>
    </ul>
  </div>
  
  <Education />
</template>

<script setup>
import { ref } from 'vue';
import contactInfo from '../data/contact.js';
import socialLinks from '../data/social.js';
import languagesList from '../data/languages.js';
import personalDetails from '../data/personalDetails.js';
import Education from './Education.vue'

// Основная информация о пользователе
const userInfo = ref({
  id: 'natali',
  image: '/assets/image.jpg',
  name: 'Nataliya Yarosh', 
  mainInfo: 'Website software developer using modern Shopify, Wordpress, HTML5, CSS3 and JavaScript. Creating modern, easy-to-use, user-friendly websites and applications; Building state-of-the-art, easy to use, user friendly web sites and applications.'
});
</script>

<style scoped>
/* Стили для основной информации */
.main-info{
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-bottom: 25px;
}

.main-info__wrap-img{
  padding: 5px;
  border-radius: 20px;
  background-color: var(--color-bg-white, #fff);
  width: 100px;
  height: 100px;
  margin-bottom: 12px;
}

.main-info__img{
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 15px;
}

.main-info__title{
  margin-top: 0;
  margin-bottom: 5px;
  font-family: var(--font-heading, 'Outfit'), sans-serif;
  font-size: var(--font-size-xl, 23px);
  color: var(--color-text-dark, #2E2E48);
}

.main-info__text{
  margin-top: 0;
  margin-bottom: 0;
  text-align: center;
  font-family: var(--font-body, 'DM Sans'), sans-serif;
  font-size: var(--font-size-sm, 14px);
  line-height: 1.4;
  color: var(--color-text-light, #47516B);
}

/* Стили для прочей информации */
.divider{
  margin-bottom: 25px;
  padding-bottom: 25px;
  border-bottom: 1px solid var(--color-border, #E2E6EE);
}

.info{
  margin: 0;
  padding: 0;
  list-style: none;
}

.info__title{
  margin-top: 0;
  margin-bottom: 15px;
  font-family: var(--font-heading, 'Outfit'), sans-serif;
  font-size: var(--font-size-md, 16px);
  color: var(--color-text-dark, #2E2E48);
}

.info__item{
  display: grid;
  grid-template-columns: 15% 85%;
  align-items: flex-start;
  margin-bottom: 15px;
}

.info__wrap-img{
  display: flex;
  justify-content: center;
  align-items: center;
}

.info__text{
  margin-top: 0;
  margin-bottom: 5px;
  font-family: var(--font-body, 'DM Sans'), sans-serif;
  font-weight: 600;
  font-size: var(--font-size-sm, 14px);
  color: var(--color-text-dark, #2E2E48);
}

.info__link{
  margin-top: 0;
  margin-bottom: 0;
  font-family: var(--font-body, 'DM Sans'), sans-serif;
  font-size: var(--font-size-sm, 14px);
  line-height: 1.3;
  color: var(--color-text-light, #47516B);
}

.info__link a{
  color: var(--color-text-light, #47516B);
  text-decoration: none;
}

.underline a{
  text-decoration: underline;
}

.info__details-item{
  margin-bottom: 10px;
  font-family: var(--font-body, 'DM Sans'), sans-serif;
  font-size: var(--font-size-sm, 14px);
  color: var(--color-text-light, #47516B);
}

.info__details-name{
  font-weight: 600;
  color: var(--color-text-dark, #2E2E48);
}

@media (max-width: 870px){
  .info__item{
    grid-template-columns: 10% 90%;
  }
}
</style>