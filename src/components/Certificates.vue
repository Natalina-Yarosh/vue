<template>
    <h2 class="item__title">{{ title }}</h2>
      <ul class="certificates">
        <li class="certificate" v-for="certificate in certificates" :key="certificate.id">
            <div class="certificate__wrap-img">
              <img :src="certificate.image" :alt="certificate.name">
            </div>
            <div class="certificate__wrap-info">
              <p class="certificate__name">{{ certificate.name }}</p>
              <p class="certificate__description">{{ certificate.description }}</p>
            </div>
            <p class="certificate__years">{{ certificate.years }}</p>
        </li>
    </ul>
</template>

<script>
export default {
  data() {
    return {
      title: 'Certificates & Awards',
      certificates: [
        {
          id: 'tms',
          image: '/assets/certificates/1.svg',
          name: 'TeachMeSkills',
          description: 'Front End developer',
          years: 'Dec 2018 - Sept 2019',
        },
        {
          id: 'udemy',
          image: '/assets/certificates/2.svg',
          name: 'Udemy',
          description: 'Vue - The Complete Guide',
          years: 'Sept 2023 - Now'
        },
      ],
    };
  },
};

</script>


<style scoped>

.item__title{
  color: #2E2E48;
  font-size: 23px;
  font-weight: 500;
  line-height: 1; 
  letter-spacing: 0.12px;
  margin-bottom: 20px;
}

.certificates{
  display: grid;
  row-gap: 20px;
}

.certificate {
  display: grid;
  grid-template-columns: 50px 1fr 200px;
  gap: 10px;
  background: #F7F9FC;
  padding: 20px 25px;

  @media (max-width:767px) {
    grid-template-columns: 1fr;
  }
}

.certificate:first-child{
  border-radius: 10px 10px 0  0 ;
}

.certificate:last-child{
  border-radius: 0 0 10px 10px ;
}

.certificate__wrap-img{
  aspect-ratio: 1;
}

.certificate__wrap-img img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.certificate__name {
  color: #79819A;
  font-size: 16px;
  font-weight: 400;
  line-height: 1;
  letter-spacing: 0.067px;
  font-family: 'DM Sans', sans-serif;
  margin-bottom: 5px;
}

.certificate__description {
  color: #2E2E48;
  font-size: 18px;
  font-weight: 500;
  line-height: 1;
  font-family: 'DM Sans', sans-serif;
}

.certificate__years {
  color: #47516B;
  font-size: 16px;
  font-weight: 400;
  line-height: 1;
  letter-spacing: 0.058px;
  font-family: 'DM Sans', sans-serif;
}
</style>
