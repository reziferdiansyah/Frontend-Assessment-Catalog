<template>
  <div class="wrap-about">
    <div class="grid-container">
    <h1>VISI</h1>
    <div>{{ fetchStaticDataVisi }}</div>
    <h1>MISI</h1>  
    <div>
      <li v-for="datas in fetchStaticDataMisi">
        {{ datas.description }}
     </li>
  </div>
</div></div>
</template>

<script>
definePageMeta({
   layout: 'homepage'
})

export default {
    data() {
      const staticMisi = [
        {
          id: 1,
          description : "Berinvestasi dalam pengembangan produk berkarakter serta memperhatikan kriteria untuk menjadi yang terbaik.",
        },
        {
          id: 2,
          description : "Mengembangkan sistem waralaba, e-commerce.",
        },
        {
          id: 3,
          description : "Memperluas cakupan kriteria produk  tema, untuk teknis, lifestyle dan adventure.",
        },
        {
          id: 4,
          description : "Memperluas pemasaran produk di showroom dan online.",
        },
        {
          id: 5,
          description : "Menyediakan produk-produk berkualitas dan memuaskan untuk kebutuhan pelanggan.",
        },
      ];
      return {
        fetchStaticDataMisi: staticMisi,
        fetchStaticDataVisi : 'Menjadi sebuah produk mendunia dalam produk khususnya lifestyle. Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industrys standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.'
      };
    },
  };
</script>

<style scoped>
.wrap-about {
    padding: 35px;
    overflow-y: scroll;
    margin-bottom: 50px;
}
.grid-container {
  background-color: mintcream;
  display: grid;
  gap: 50px;
  grid-template-columns: auto auto;
}

/* Desktop Version */
@media (max-width: 768px) {
   .grid-container {
      grid-template-columns: auto auto;
      gap: 50px;
    }
  }
  /* Mobile Version */
  @media (max-width: 480px) {
    .grid-container {
      grid-template-columns: auto;
      gap: 20px;
    }
  }
</style>
