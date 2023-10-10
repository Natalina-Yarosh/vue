<template>
  <div class="item">
    <h2 class="item__title">{{ title }}</h2>
      <ul class="educations">
        <li class="education" v-for="education in educations" :key="education.id">
          <div class="education__head">
            <div class="education__wrap-img">
              <img :src="education.image" :alt="education.name">
            </div>
            <p class="education__name">{{ education.name }}</p>
          </div>
          <h3 class="education__fullname">{{ education.fullname }}</h3>
          <p class="education__years">{{ education.years }}</p>
          <p class="education__info">
            <span class="education__percentage">Percentage - </span>
            {{ education.percentage }}
          </p>
        </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Education',
      educations: [
      {
          id: 'BNTU',
          image: 'assets/education/1.svg',
          name: 'Belarusian National Technical University',
          fullname: 'Engineering Pedagogical Faculty',
          years: '2013 - 2017',
          percentage: '98%',
        },
      ],
    };
  },
};

</script>


<style scoped>
.item{
  margin-bottom: 24px;
}

.item__title{
  color: #2E2E48;
  font-size: 23px;
  font-weight: 500;
  line-height: 1; 
  letter-spacing: 0.12px;
  margin-bottom: 20px;
}

.educations{
  list-style: none;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;

  @media (max-width:1025px) {
    grid-template-columns: repeat(2, 1fr);
  }

  @media (max-width:767px) {
    grid-template-columns: 1fr;
  }
}

.education{
  padding: 16px 24px;
  background:  #F7F9FC;

  @media (max-width:767px){
    padding: 14px 18px;
  }
}

.education:first-child{
  border-radius: 4px 0 0  4px;
}
.education:last-child{
  border-radius: 0 4px 4px 0;
}

.education__head {
  display: grid;
  grid-template-columns: 40px 1fr;
  column-gap: 8px;
  align-items: center;
  margin-bottom: 10px;
}

.education__wrap-img {
  width: 100%;
  display: flex;
}

.education__wrap-img img {
  width: 100%;
  height: auto;
  object-fit: contain;
  object-position: center;
}

.education__name {
  font-family: 'DM Sans', sans-serif;
  color: #2E2E48;
  font-size: 17px;
  font-weight: 500;
  line-height: 21px;

  @media (max-width:767px){
    font-size: 15px;
    line-height: 17px;
  }
}

.education__fullname {
  color: #2E2E48;
  font-size: 18px;
  font-style: normal;
  font-weight: 600;
  line-height: 22px;
  font-family: 'DM Sans', sans-serif;
  margin-bottom: 6px;

  @media (max-width:767px){
    font-size: 16px;
    line-height: 18px;
  }
}

.education__years {
  color: #79819A;
  font-family: 'DM Sans', sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 1;
  letter-spacing: 0.05px;
  margin-bottom: 5px;

  @media (max-width:767px){
    font-size: 14px;
  }
}

.education__info {
  color: #79819A;
  font-family: 'DM Sans', sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 1;
  letter-spacing: 0.06px;

  @media (max-width:767px){
    font-size: 14px;
  }
}

.education__percentage{
  color:  #5D5FEF;
}
</style>
