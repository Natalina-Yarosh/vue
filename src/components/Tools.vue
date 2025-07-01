<template>
  <h2 class="item__title">{{ title }}</h2>
    <ul class="tools">
      <li class="tool" v-for="tool in tools" :key="tool.id">
          <div class="tool__wrap-img">
            <img :src="tool.image" :alt="tool.name">
          </div>
          <p class="tool__name">{{ tool.name }}</p>
          <p class="tool__description">{{ tool.description }}</p>
      </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      title: 'Tools/Skills',
      tools: [
        {
          id: 'html',
          image: '/assets/tools/3.png',
          name: 'HTML 5',
          description: 'Structural Design',
        },
        {
          id: 'css',
          image: '/assets/tools/4.png',
          name: 'CSS 3',
          description: 'Style Design',
        },
        {
          id: 'js',
          image: '/assets/tools/9.png',
          name: 'Java script',
          description: 'Scripting language',
        },
        {
          id: 'wordpress',
          image: '/assets/tools/5.png',
          name: 'Wordpress',
          description: 'Web development',
        },
        {
          id: 'shopify',
          image: '/assets/tools/8.png',
          name: 'Shopify',
          description: 'Web development',
        },
        {
          id: 'vscode',
          image: '/assets/tools/6.png',
          name: 'VS Code',
          description: 'Code editor',
        },
        {
          id: 'figma',
          image: '/assets/tools/1.svg',
          name: 'Figma',
          description: ' UI Design, prototyping',
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

.tools{
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  list-style: none;

  @media (max-width:767px) {
    gap: 10px;
  }
}

.tool:nth-child(-n+3){
  width: calc((100% - 40px) / 3);

  @media (max-width:767px) {
    width: calc((100% - 10px) / 2);
  }
}

.tool{
  width: calc((100% - 60px) / 4);
  background: #F7F9FC;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  row-gap: 10px;
  padding: 20px;

  @media (max-width:767px) {
    width: calc((100% - 10px) / 2);
  }
}
.tool:first-child{
  border-radius: 10px 0 0 0;

  @media (max-width:767px) {
    border-radius: 0;
  }
}
.tool:nth-child(3){
  border-radius: 0 10px 0 0 ;

  @media (max-width:767px) {
    border-radius: 0;
  }
}

.tool:nth-last-child(4){
  border-radius: 0 0 0 10px;

  @media (max-width:767px) {
    border-radius: 0;
  }
}

.tool:first-child{
  border-radius: 10px 0 0 0;

  @media (max-width:767px) {
    border-radius: 0;
  }
}

.tool:last-child{
  border-radius:  0 0 10px 0;

  @media (max-width:767px) {
    border-radius: 0;
  }
}

.tool__wrap-img{
  width: 100%;
  height: 100px;
  display: flex;
  align-items: center;
  justify-content: center;

  @media (max-width:1025px) {
    height: 70px;
  }
}

.tool__wrap-img img{
  width: 100%;
  height: 100%;
  object-fit: scale-down;
}

.tool__name {
  width: 100%;
  text-align: center;
  color: #2E2E47;
  font-family: 'DM Sans', sans-serif;
  font-size: 16px;
  font-style: normal;
  font-weight: 500;
  line-height: 1;
}

.tool__description {
  color: #79819A;
  font-family: 'DM Sans', sans-serif;
  font-size: 15px;
  font-weight: 400;
  line-height: 1;
  letter-spacing: 0.05px;
  text-align: center;

  @media (max-width:767px) {
    font-size: 14px;
  }
}

</style>
