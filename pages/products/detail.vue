<template>
<div class="wrap-detail">
 <p style="margin-bottom: 20px;"> <a href="/">Home</a> > Products > Name Products </p>
  <!-- CARD CONTENT -->
   <div class="card-wrapper">
    <div class="card">
    <!-- CARD LEFT PREVIES IMAGES -->
    <div class="product-imgs">
    <!-- BIG -->
     <Carousel 
      :autoplay="5000"
      id="gallery"
      :items-to-show="1"
      :wrap-around="true" v-model="currentSlide">
     <Slide v-for="slide in fetchStaticImg" :key="slide.id">
       <div class="carousel__item">
          <img  style="width: 320px !important; height: 320px !important;" :alt="slide.alt" :src="slide.path" />
        </div>
     </Slide>
    </Carousel>
    <!-- PREVIEW -->
    <Carousel
    id="thumbnails"
    :items-to-show="3"
    :wrap-around="true"
    v-model="currentSlide"
    ref="carousel"
  >
    <Slide v-for="slideThumbnails in fetchStaticImg" :key="slideThumbnails.id">
      <div class="carousel__item" @click="slideTo(slideThumbnails.id - 1)">
          <img style="width: 150px !important; height: 150px !important;" :alt="slideThumbnails.alt" :src="slideThumbnails.path" />
      </div>
    </Slide>
   </Carousel>
   </div>
  <!-- CAROUSEL IMAGES -->

     <!-- CARD RIGHT INFORMATION -->
     <div>
      <div class="name-product">Name Products</div>
   
      <div class="product-price">
        <p class="new-price">Price: <span>RP. 2.490.000</span></p>
      </div>

      <div class="product-detail">
        <h2>about this item: </h2>
        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>
        <p><b>Color: </b> <span>Black</span></p>
        <p><b>Available</b>: <span>in stock</span></p>
        <p><b>Size</b>: <span>Available From 30 to 50</span></p>
        <p><b>Category: </b><span>Shoes</span></p>
        <p><b>Shipping Area: </b> <span>All over the world</span></p>
        <p><b>Shipping Fee: </b> <span>Free</span></p>
      </div>

      <div class="purchase-info">
       Amount : <input type="number" placeholder="Amount" min="0" v-model="AmountData">
       Size : <input type="number" placeholder="Size" min="30" max="50" v-model="SizeData">
       <br>
          <button  @click="myFunction" type="button" class="btn">
          Add to Cart <i class="fas fa-shopping-cart"></i>
        </button>
      </div>
    </div>
   </div>
  </div>
</div>
</template>
  
<script>
import { defineComponent } from 'vue'
import { Carousel, Slide } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'
  definePageMeta({
     layout: 'homepage'
  })
  export default {
     components: {
     Carousel,
     Slide,
    },
      data() {

      const staticImages = [
      {
        id: 1,
        type: "mobile",
        path: "https://d1yutv2xslo29o.cloudfront.net/product/variant/photo/58f8628e-0e3e-4896-94b0-afc8ebc32c79.jpg",
        alt: "Images 1",
      },
      {
        id: 2,
        type: "mobile",
        path: "https://d1yutv2xslo29o.cloudfront.net/product/variant/photo/a0663f7d-cc30-48e4-8306-98809148b569.jpg",
        alt: "Images 2",
      },
      {
        id: 3,
        type: "mobile",
        path: "https://d1yutv2xslo29o.cloudfront.net/product/variant/photo/6ed02914-d48c-4963-b23c-c9206b56b604.jpg",
        alt: "Images 3",
      },
      {
        id: 4,
        type: "mobile",
        path: "https://d1yutv2xslo29o.cloudfront.net/product/variant/photo/751f514c-af22-4a26-85e3-86dde4218c2b.jpg",
        alt: "Images 3",
      },
      {
        id: 5,
        type: "mobile",
        path: "https://d1yutv2xslo29o.cloudfront.net/product/variant/photo/6660e58a-c0db-4a33-bbec-c695624f7d66.jpg",
        alt: "Images 3",
      },
    ];
        return {
          AmountData : 1,
          SizeData : 30,
          currentSlide: 0,
          fetchStaticImg: staticImages,
        };
      },
      methods: { 
        myFunction() {
          const SizeFix = this.SizeData
          const AmoutFix = this.AmountData
          alert(`Amount ${AmoutFix} and Size ${SizeFix} Already add to Cart`);
        },
        slideTo(val) {
         this.currentSlide = val;
        },
      }
    };

</script>

<style scoped>
 a {
  color: black;
 }
.wrap-detail {
    padding: 35px;
    overflow-y: scroll;
    margin-bottom: 50px;
}
.card-wrapper{
    max-width: 1100px;
    margin: 0 auto;
}
img{
    width: 100%;
    display: block;
}
.img-display{
    overflow: hidden;
}
.img-showcase{
    display: flex;
    width: 100%;
    transition: all 0.5s ease;
}
.img-showcase img{
    min-width: 100%;
}
.img-select{
    display: flex;
}
.img-item{
    margin: 0.3rem;
}
.img-item:nth-child(1),
.img-item:nth-child(2),
.img-item:nth-child(3){
    margin-right: 0;
}
.img-item:hover{
    opacity: 0.8;
}
.name-product{
    text-decoration: none;
    text-transform: uppercase;
    font-weight: 400;
    font-size: 1.9rem;
    display: inline-block;
    margin-bottom: 0.5rem;
    background: #ff4d25;
    color: #fff;
    padding: 0 0.3rem;
    transition: all 0.5s ease;
}
.name-product:hover{
    opacity: 0.9;
}

.product-price{
    margin: 1rem 0;
    font-size: 1rem;
    font-weight: 700;
}
.product-price span{
    font-weight: 400;
}
.last-price span{
    color: #f64749;
    text-decoration: line-through;
}
.new-price span{
    color:  #ff4d25;
}
.product-detail h2{
    text-transform: capitalize;
    color: #12263a;
    padding-bottom: 0.6rem;
}
.product-detail p{
    font-size: 0.9rem;
    padding: 0.3rem;
    opacity: 0.8;
}
.purchase-info{
    margin: 1.5rem 0;
}
.purchase-info input,
.purchase-info .btn{
    border: 1.5px solid #ddd;
    border-radius: 25px;
    text-align: center;
    padding: 0.45rem 0.8rem;
    outline: 0;
    margin-right: 0.2rem;
    margin-bottom: 1rem;
}
.purchase-info input{
    width: 60px;
}
.purchase-info .btn{
    cursor: pointer;
    color: #fff;
}
.purchase-info .btn:last-of-type{
    background: #333;
}
.purchase-info .btn:hover{
    opacity: 0.9;
}
@media screen and (min-width: 992px){
    .card{
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        grid-gap: 1.5rem;
    }
    .card-wrapper{
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .product-imgs{
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
}
</style>
  