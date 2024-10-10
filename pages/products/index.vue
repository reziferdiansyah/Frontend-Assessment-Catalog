<template>
   <div class="wrap-card">
    <!-- LIST  -->
     <div style="text-align: center;">
          <h1 style="text-transform: uppercase;">
            our products
          </h1>
      </div>
      <div class="card-container">
          <div v-for="datas in productsList.data" class="card" @click="goToPasaran">
      <div class="text-content-info">
        <div class="box-images-products"> 
          <img style="width: 100%; height: 100%;" :src="datas.path" :alt="datas.alt">
        </div>
        <p>
         {{ datas.name }}
        </p>
        <p>
         RP : {{ datas.price }}
        </p>
      </div>
          </div>
      </div>
  </div>
  </template>
  
  
  <script>
  export default {
    data() {
      return {
        productsList : '',
      };
    },
    async mounted() {
      this.productsList = await $fetch('https://dummyjson.com/c/4818-ca90-4949-8844')
    },
    methods: {
      goToPasaran() {
        this.$router.push('/products/detail')
      },
    } 
  };
  </script>
  
  <style scoped>
  .box-images-products { 
    background-color: white;
    padding: 20px;
  }
  .text-content-info{
    justify-content: center;
    text-align: center;
  }
  .wrap-card {
    padding: 35px;
    overflow-y: scroll;
    margin-bottom: 50px;
  }
  .card-container {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
  }
  .card {
      flex: 1 1 calc(25% - 20px);
      box-sizing: border-box;
      border: 1.5px solid whitesmoke;
      cursor: pointer;
  }
  .card:hover {
     background-color: whitesmoke;
  }
  /* Desktop Version */
  @media (max-width: 768px) {
      .card {
          flex: 1 1 calc(50% - 20px);
      }
  }
  /* Mobile Version */
  @media (max-width: 480px) {
      .card {
          flex: 1 1 calc(50% - 20px);
      }
  }
  </style>