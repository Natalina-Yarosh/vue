<template>
  <div class="item">
    <h2 class="item__title">{{ title }}</h2>
      <ul class="projects">
        <li class="project" v-for="project in projects" :key="project.id">
            <div class="project__wrap-img">
              <img :src="project.image" :alt="project.name">
            </div>
            <div class="project__wrap-info">
              <h3 class="project__name">{{ project.name }}</h3>
              <p class="project__description">{{ project.description }}</p>
            </div>
            <div class="project__wrap-link">
              <div class="project__svg">
                <svg width="8" height="8" viewBox="0 0 8 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M2.89532 6.48385C2.26339 6.48385 1.69369 6.10319 1.45182 5.51939C1.20995 4.93558 1.34355 4.26356 1.79032 3.81666L2.45344 3.15353L2.89532 3.59541L2.23251 4.25822C1.99565 4.49508 1.90315 4.8403 1.98984 5.16385C2.07654 5.4874 2.32926 5.74013 2.65281 5.82682C2.97636 5.91352 3.32159 5.82101 3.55844 5.58416L4.22126 4.92134L4.66313 5.36353L4.00032 6.02635C3.70784 6.32026 3.30996 6.48499 2.89532 6.48385ZM3.11626 5.14228L2.67438 4.70041L4.88407 2.49072L5.32594 2.93259L3.11657 5.14197L3.11626 5.14228ZM5.54719 4.47947L5.10501 4.03759L5.76782 3.37478C6.0079 3.13864 6.10288 2.79186 6.01664 2.46634C5.93041 2.14081 5.6762 1.88655 5.3507 1.80023C5.02519 1.71392 4.6784 1.80882 4.44219 2.04884L3.77907 2.71166L3.33719 2.26978L4.00032 1.60666C4.61128 1.00102 5.59687 1.00318 6.20518 1.61148C6.81348 2.21979 6.81564 3.20538 6.21001 3.81634L5.54719 4.47916V4.47947Z" fill="#516CF7"/>
                </svg>
              </div>
              <a class="project__link" :href="project.Path">{{ project.linkName }}</a>
            </div>
        </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Latest projects',
      projects: [
        {
          id: 'project1',
          image: '/assets/projects/1.svg',
          name: 'Project 1',
          description: 'Website for the clinic that is specialized in different services such as mammalogy, laser surgery, laser cosmetology, etc. The possibility to make an appointment is realized, as well as a brief overview of services, doctors, and the whole clinic.',
          linkPath: '#',
          linkName: 'project 1',
        },
        {
          id: 'project2',
          image: '/assets/projects/1.svg',
          name: 'Project 2',
          description: 'Web application for special event (new auto models presentation), where early birds can buy tickets and make an experiment with cars (change vehicles colors and etc.)',
          linkPath: '#',
          linkName: 'project 2',
        },
        {
          id: 'project3',
          image: '/assets/projects/1.svg',
          name: 'Project 3',
          description: 'Website and webshop of the famous sportswear and shoe manufacturer.',
          linkPath: '#',
          linkName: 'project 3',
        },
        {
          id: 'project4',
          image: '/assets/projects/1.svg',
          name: 'Project 4',
          description: 'Develop HTML templates of emails for marketing and notification campaigns of credit organization.',
          linkPath: '#',
          linkName: 'project 4',
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

.projects {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  list-style: none;

  @media (max-width:767px) {
    grid-template-columns: 1fr;
  }
}

.project {
  padding: 20px;
  background: #F7F9FC;
  display: grid;
  grid-template-columns: 60px 1fr;
  gap: 10px;

  @media (max-width:767px) {
    grid-template-columns: 50px 1fr;
  }
}

.project:first-child{
  border-radius: 20px 0 0 0;

  @media (max-width:767px) {
    border-radius: 20px 20px 0 0;;
  }
}
.project:nth-child(2){
  border-radius: 0 20px 0 0;

  @media (max-width:767px) {
    border-radius: 0;
  }
}

.project:nth-child(n-1){
  border-radius: 0 0 0 20px;

  @media (max-width:767px) {
    border-radius: 0;
  }
}

.project:last-child{
  border-radius: 0 0 20px 0;

  @media (max-width:767px) {
    border-radius: 0 0 20px 20px;
  }
}

.project__wrap-img {
  aspect-ratio: 1;
  display: flex;
}

.project__wrap-img img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  object-position: center;
}

.project__name {
  color: #2E2E48;
  font-size: 18px;
  font-weight: 500;
  line-height: 1;
  font-family: 'DM Sans', sans-serif;
  margin-bottom: 10px;

  @media (max-width:767px) {
    font-size: 16px;
  }
}

.project__description {
  color: #79819A;
  font-size: 16px;
  font-weight: 400;
  line-height: 18px;
  letter-spacing: 0.07px;
  font-family: 'DM Sans', sans-serif;

  @media (max-width:767px) {
    font-size: 14px;
    line-height: 16px;
  }
}

.project__wrap-link{
  grid-column: 1/3;
  display: flex;
  align-items: center;
  column-gap: 5px;
  cursor: pointer;
}

.project__svg {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #E1E7FE;
}

.project__svg svg{
  width: 70%;
  height: 70%;
  transition: all .3s;
}

.project__link {
  color: #516CF7;
  font-size: 16px;
  font-weight: 600;
  line-height: 1;
  text-decoration-line: underline;
  font-family: 'DM Sans', sans-serif;
  

  @media (max-width:767px) {
    font-size: 14px;
    line-height: 16px;
  }
}

.project__wrap-link:hover .project__svg svg{
  transform: scale(1.1);
}
.project__wrap-link:hover .project__link{
  color: #303644;
}
</style>
