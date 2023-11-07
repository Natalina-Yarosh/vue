<template>
  <div class="item-circle"></div>
  <h2 class="item__title">{{ title }}</h2>
    <ul class="achievements">
      <li class="achievement" v-for="achievement in achievements" :key="achievement.id">
        <div class="achievement__info">
          <p class="achievement__years-online">
            <span class="achievement__yaears">{{ achievement.years }} </span>
            <svg xmlns="http://www.w3.org/2000/svg" width="6" height="7" viewBox="0 0 6 7" fill="none">
              <path d="M3 5.81666C2.68423 5.54732 2.39155 5.25204 2.125 4.93391C1.725 4.45616 1.25 3.74466 1.25 3.06666C1.24965 2.35855 1.67606 1.72001 2.33027 1.44901C2.98447 1.17801 3.73752 1.32797 4.238 1.82891C4.56712 2.15656 4.75148 2.60226 4.75001 3.06666C4.75001 3.74466 4.275 4.45616 3.875 4.93391C3.60845 5.25204 3.31577 5.54732 3 5.81666ZM3 2.31666C2.73205 2.31666 2.48446 2.45961 2.35048 2.69166C2.21651 2.92371 2.21651 3.20961 2.35048 3.44166C2.48446 3.67371 2.73205 3.81666 3 3.81666C3.41421 3.81666 3.75 3.48088 3.75 3.06666C3.75 2.65245 3.41421 2.31666 3 2.31666Z" fill="#79819A"/>
            </svg>
            Online
          </p>
          <div class="achievement__wrap">
            <div class="achievement__wrap-img">
              <img :src="achievement.image" :alt="achievement.name">
            </div>
            <div class="achievement__wrap-company">
              <p class="achievement__contributor">{{ achievement.contributor }}</p>
              <p class="achievement__name">{{ achievement.name }}</p>
            </div>
          </div>
        </div>
        <p class="achievement__description">{{ achievement.description }}</p>
      </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      title: 'Achievements',
      achievements: [
        {
          id: 'plavno',
          years: 'Sept 2019 - Now',
          image: '/assets/achievements/1.svg',
          contributor: 'Contributor',
          name: 'Plavno',
          description: 'Contributed 12 PR’s in various open source projects. Great experience and learning alot about working with Github. Connecting with developers',
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
  margin-bottom: 30px;
}

.achievements{
  @media (max-width:767px) {
    display: grid;
    row-gap: 20px;
  }
}

.achievement{
  padding: 6px 0 20px 40px;
  list-style: none;
  display: grid;
  grid-template-columns: 40% 1fr;
  column-gap: 20px;
  position: relative;

  @media (max-width:767px) {
    grid-template-columns: 1fr;
    row-gap: 10px;
    padding: 0;
  }
}

.achievement::before{
  content: '';
  position: absolute;
  left: 20px;
  top: 27px;
  height: calc(100% - 27px);
  display: block;
  width: 0.5px;
  background-color: #F7F9FC;
}

.achievement::after{
  content: '';
  position: absolute;
  left: 20px;
  top: 12px;
  transform: translateX(-50%);
  height: 3.5px;
  width: 3.5px;
  display: block;
  background-color: #2E2E48;
  border-radius: 50%;
}

.achievement__years-online{
  color: #79819A;
  font-family: 'DM Sans', sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 1;
  letter-spacing: 0.05px;
  margin-bottom: 10px;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  column-gap: 3px;
}

.achievement__yaears{
  color:#47516B;
}

.achievement__years-online svg{
  width: 17px;
  height: 19px;
}

.achievement__wrap{
  display: grid;
  grid-template-columns: 70px 1fr;
  column-gap: 20px;
  align-items: center;
}

.achievement__wrap-img{
  width: 70px;
  height: 70px;
  display: flex;
}

.achievement__wrap-img img{
  width: 100%;
  height: 100%;
  object-fit: contain;
  object-position: center;
}

.achievement__contributor{
  color: #79819A;
  font-family: 'DM Sans', sans-serif;
  font-size: 18px;
  font-weight: 400;
  line-height: 1; 
  letter-spacing: 0.06px;
  margin-bottom: 5px;
}

.achievement__name{
  color: #2E2E48;
  font-family: 'DM Sans', sans-serif;
  font-size: 18px;
  font-weight: 500;
  line-height: 1; 
}

.achievement__description{
  color: #79819A;
  font-family: 'DM Sans', sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 18px;
  letter-spacing: 0.05px;

  @media (max-width:767px) {
    font-size: 14px;
    line-height: 16px;
  }
}

@media (max-width:767px){
  .achievement::before,
  
  .achievement::after{
    content: none;
  }
}
</style>
