<template>
  <div class="banner">
    <Carousel :autoplay="2000" :wrap-around="true">
      <Slide v-for="slide in fetchStaticImg" :key="id">
        <img :src="slide.path" :alt="slide.alt ">
        <!-- <div class="carousel__item">{{ slide.alt }}</div> -->
      </Slide>
  
      <template #addons>
        <Pagination />
      </template>
    </Carousel>
  </div>
  </template>
  
  <script>
  import { defineComponent } from 'vue'
  import { Carousel, Pagination, Slide } from 'vue3-carousel'
  import 'vue3-carousel/dist/carousel.css'
  
  export default defineComponent({
    name: 'Autoplay',
    components: {
      Carousel,
      Slide,
      Pagination,
    },

    data() {
    const staticImages = [
      {
        id: 1,
        type: "mobile",
        path: "",
        alt: "Images 1",
      },
      {
        id: 2,
        type: "mobile",
        path: "",
        alt: "Images 2",
      },
      {
        id: 3,
        type: "mobile",
        path: "",
        alt: "Images 3",
      },
    ];
    return {
      currentSlide: 0,
      fetchStaticImg: staticImages,
    };
  },
  })
  </script>

<style scoped>
.banner {
  padding: 20px;
  background-color: red;
}
</style>
  