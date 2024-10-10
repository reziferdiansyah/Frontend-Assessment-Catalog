<template>
   <div class="wrap-card">
     <div style="text-align: center;">
          <h1 style="text-transform: uppercase;">
            our products
          </h1>
      </div>
      <div class="card-container">
          <div v-for="datas in fetchStaticData" class="card">
      <div class="text-content-info">
        <div class="box-images-products"> 
          <img style="width: 100%; height: 100%;" :src="datas.path" :alt="datas.alt">
        </div>
        <p>
         {{ datas.description }}
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
      const staticProducts = [
        {
          id: 1,
          price : "10,000",
          description : "Lorem ipsum 1",
          path: "https://img.kwcdn.com/product/Fancyalgo/VirtualModelMatting/2310f917cea6690cc9b3805e939d5121.jpg?imageView2/2/w/800/q/70/format/webp",
          alt: "Images 1",
        },
        {
          id: 2,
          price : "20,000",
          description : "Lorem ipsum 2",
          path: "https://encrypted-tbn0.gstatic.com/shopping?q=tbn:ANd9GcSFfPGlrOpbxIhVkdcZYlBksgwMJVP_823XjqQBhnB1LTPB6vNtFwd0KNSGAKCJ4I38Pjl16z1E8gZRJfOwa12jn2sJBfwiHw9S3D3niApTWN3BYO_8JCiSYg&usqp=CAc",
          alt: "Images 2",
        },
        {
          id: 3,
          price : "30,000",
          description : "Lorem ipsum 3",
           path: "https://areioutdoorgear.co.id/wp-content/uploads/2022/12/IMG-20211113-WA0053.jpg",
          alt: "Images 3",
        },
        {
          id: 4,
          price : "40,000",
          description : "Lorem ipsum 4",
          path: "https://d1yutv2xslo29o.cloudfront.net/product/variant/photo/b4e1c844-ed47-4deb-bcac-a52b8359cd9d.jpg",
          alt: "Images 4",
        },
      ];
      return {
        fetchStaticData: staticProducts,
      };
    },
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