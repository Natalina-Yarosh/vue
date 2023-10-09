<template>

  <div class="main-info divider">
    <div class="main-info__wrap-img">
      <img class="main-info__img" :src='userImage' alt="user image">
    </div>
    <h1 class="main-info__title">{{ userName }}</h1>
    <p class="main-info__text">{{ userMainInfo }}</p>
  </div>

  <ul class="info divider">
    <li class="info__item" v-for="info in infos" :key='info.id'>
      <div class="info__wrap-img">
        <img :src="info.icon" :alt="info.name">
      </div>
      <div class="info__wrap-text">
        <p class="info__text">
          {{ info.name}}
        </p>
        <div :class="[ {underline: info.isUnderline}, 'info__link' ]" v-html="info.link"></div>
      </div>
    </li>
  </ul>

  <div class="socials divider"> 
    <p class="info__title">Socials</p>
    <ul class="info">
      <li class="info__item" v-for="social in socials" :key='social.id'>
        <div :class="[social.id, 'info__wrap-img']">
          <img :src="social.icon" :alt="social.name">
        </div>
        <div class="info__wrap-text">
          <p class="info__text">
            {{ social.name}}
          </p>
          <div class="info__link" v-html="social.link"></div>
        </div>
      </li>
    </ul>
  </div>

  <div class="languages divider">
    <p class="info__title">Languages</p>
    <ul class="info">
      <li class="info__item" v-for="language in languages" :key="language.id">
        <div class="info__wrap-img">
          <img :src="language.icon" :alt="language.name">
        </div>
        <div class="info__wrap-text">
          <p class="info__text">
            {{ language.name}}
          </p>
          <p class="info__link">{{ language.info }}</p>
        </div>
      </li>
    </ul>
  </div>

  <div class="hobbies divider">
    <p class="info__title">Hobbies & Interests</p>
    <ul class="info">
      <li class="info__item" v-for="hobby in hobbies" :key="hobby.id">
        <div class="info__wrap-img">
          <img :src="hobby.icon" :alt="hobby.name">
        </div>
        <div class="info__wrap-text">
          <p class="info__text">
            {{ hobby.name}}
          </p>
        </div>
      </li>
    </ul>
  </div>

  <div class="personal-details">
    <p class="info__title">Personal Details</p>
    <ul class="info"> 
      <li class="info__details-item" v-for="(productionDetail, name) in productionDetails" :key="name">
        <span class="info__details-name">{{name}}:</span> {{productionDetail}}
      </li>
    </ul>
  </div>

</template>

<script>
export default {
  data() {
    return {
      id: 'natali',
      userImage: 'src/assets/image.jpg',
      userName: 'Nataliya Yarosh', 
      userMainInfo: 'Website software developer using modern Shopify, Wordpress, HTML5, CSS3 and JavaScript. Creating modern, easy-to-use, user-friendly websites and applications; Building state-of-the-art, easy to use, user friendly web sites and applications.',
      infos: [
        {
          id: 'email',
          name: 'Email',
          icon: 'src/assets/aside/email.svg',
          link:`<a href="mailto:natali.yarosh.sergeevna@gmail.com">natali.yarosh.sergeevna@gmail.com</a>`,
          isUnderline: false,
        },
        {
          id: 'website',
          name: 'Website',
          icon: 'src/assets/aside/website.svg',
          link: `<a href="https://anuragyadav365.github.io/portfolio.html">https://anuragyadav365.github.io/portfolio.html</a>`,
          isUnderline: true,
        },
        {
          id: 'phone',
          name:'Phone',
          icon: 'src/assets/aside/phone.svg',
          link: `<a href="tel:(+48)881233980">(+48) 881 233 980</a>`,
          isUnderline: false,
        },
        {
          id: 'address',
          name: 'Address',
          icon: 'src/assets/aside/address.svg',
          link: '<p>Poznań, Poland</p>',
          isUnderline: false,
        }
      ],
      socials: [
        {
          id:'instagram',
          name: 'Instagram',
          icon: 'src/assets/aside/instagram.svg',
          link: `<a href='https://www.instagram.com/it.wwwoman'>@it.wwwoman</a>`
        },
        {
          id:'github',
          name: 'Github',
          icon: 'src/assets/aside/github.svg',
          link: `<a href='https://github.com/Natalina-Yarosh' target='_blank'>@Natalina-Yarosh</a>`
        },
        {
          id:'linkedin',
          name: 'Linkedin',
          icon: 'src/assets/aside/linkedin.svg',
          link: `<a href='https://www.linkedin.com/in/natali-yarosh-57b61a183/' target='_blank'>Natali Yarosh</a>`,
        }
      ],
      languages:[
      {
          id:'spanish',
          name: 'Spanish',
          icon: 'src/assets/aside/spanish.svg',
          info: 'Elementary'
        },
        {
          id:'english',
          name: 'English',
          icon: 'src/assets/aside/english.svg',
          info: 'Intermediate'
        },
        {
          id:'polish',
          name: 'Polish',
          icon: 'src/assets/aside/polish.png',
          info: 'Intermediate'
        }
      ],
      hobbies:[
        {
          id:'teaching',
          name: 'Teaching',
          icon: 'src/assets/aside/gaming.svg',
        },
        {
          id:'travelling',
          name: 'Travelling',
          icon: 'src/assets/aside/travelling.svg',
        },
        {
          id:'blogging',
          name: 'Blogging',
          icon: 'src/assets/aside/blogging.svg',
        },
      ],
      productionDetails: {
          'Mother’s Name': 'Tatyana Yarosh',
          'Father’s Name': 'Sergey Yarosh',
          'D.O.B.': '23 - 04 - 1996',
      }
    };
  },
};

</script>

<style scoped>
.divider{
  padding-bottom: 16px;
  margin-bottom: 16px;
  border-bottom: 0.5px solid #E2E6EE;
}

.underline{
  text-decoration: underline;
}

.main-info{
  text-align: left;

  @media (max-width:870px) {
    grid-column: 1/3;
  }
}
.main-info__wrap-img{
  width: 100px;
  height: 100px;
  border-radius: 50%;
  overflow: hidden;
  margin-bottom: 30px;
}

.main-info__img{
  object-fit: cover;
  object-position: center;
  width: 100%;
  height: 100%;
}

.main-info__title{
  font-size: 30px;
  font-weight: 500;
  line-height: 1; 
  letter-spacing: -0.32px;
  margin-bottom: 30px;
  color: #2E2E48;

  @media (max-width:1025px) {
    font-size: 25px;
    margin-bottom: 25px;
  }
}

.main-info__text{
  color:  #47516B;
  font-size: 16px;
  font-weight: 500;
  line-height: 20px; 
  letter-spacing: 0.18px;
}

.info{
  list-style: none;
  text-align: left;
  display: grid;
  row-gap: 20px;
}

.info__item {
  display: grid;
  grid-template-columns: 40px 1fr;
  column-gap: 15px;
  align-items: center;

  @media (max-width:1025px) {
    column-gap: 10px;
  }
}

.info__wrap-img {
  width: 40px;
  height: 40px;
  background-color: #E2E6EE;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  object-fit: cover;
}

.info__wrap-img img{
  width: 50%;
  height: 50%;
  object-fit: contain;
  object-position: center;
}

.info__text {
  color: #79819A;
  font-size: 18px;
  font-weight: 400;
  line-height: 1;
  letter-spacing: 0.06px;
  margin-bottom: 5px;
  font-family: 'DM Sans', sans-serif;

  @media (max-width:1025px) {
    font-size: 16px;
  }
}

.info__link{
  color:  #47516B;
  font-size: 16px;
  font-weight: 500;
  line-height: 18px; 
  font-family: 'DM Sans', sans-serif;

  @media (max-width:1025px) {
    font-size: 16px;
  }
}

.info__title{
  color:  #79819A;
  font-family: 'DM Sans', sans-serif;
  font-size: 20px;
  font-weight: 400;
  line-height: 1; 
  letter-spacing: 0.06px;
  margin-bottom: 20px;

  @media (max-width:1025px) {
    font-size: 18px;
    margin-bottom: 15px;
  }
}

.personal-details .info{
  row-gap: 10px;
}

.info__details-item{
  color: #989FB2;
  font-size: 16px;
  font-weight: 500;
  line-height: 1;
  font-family: 'DM Sans', sans-serif;
}

.info__details-name{
  color: #100F0F;
}

.socials .instagram {
  background: radial-gradient(78.13% 78.13% at 50% 96.88%, rgba(140, 58, 170, 0.00) 71.35%, rgba(140, 58, 170, 0.20) 100%), radial-gradient(126.96% 126.96% at 6.47% 97.81%, #FA8F21 9%, #D82D7E 78%);
}

.socials .github{
  background:  #FFF;
}

.socials .twitter{
  background:  #00ACEE;
}

.socials .linkedin{
  background:  #0077B5;
}

.socials .info__link {
  text-decoration: underline;
}

.languages .info__wrap-img,
.hobbies .info__wrap-img{
  background: transparent;
}

.languages .info__wrap-img img{
  width: 100%;
  height: auto;
  border-radius: 2px;
}

.languages .info__text{
  font-weight: 500;
}

.languages .info__link{
  font-weight: 400;
}

.hobbies .info__text{
  margin-bottom: 0;
  font-weight: 500;
}

.hobbies .info__wrap-img img{
  width: 90%;
  height: auto;
}

.hobbies .info{
  row-gap: 8px;
}
</style>
