<!-- title : location
      Picture
      price heart
-->
<template>
<div class="wrapper">
  <div class="products">
    <div class="product" v-for="product in products" :key="product.id">
        <button v-on:click="AddtoCart(product)">
          <!--This is to create the box around the information.-->
        <div class="image">
          <img :src="'/images/products/'+product.image">
        </div>
        <div class="info">
          <h1>{{product.name}}</h1>

          <h2>{{product.price}} - {{product.location}}</h2>
            <!-- <h2>{{product.location}}</h2> -->
             <i class="far fa-heart"></i>
          </div>

        </button>
            <!--You have to pass in the prdouct-->

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductList',
  props: {
    products: Array
  },
  methods: {
    AddtoCart(product) {

      return this.$root.$data.cart.push(product); // You have to attatch it to the root. Which is why we use this syntax
      // the other cool thing about this, that you pass in the product from up above.
    }
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.products {
  /*THis makes it so the products don't bump into each other*/
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;

}

.product {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}

.product img {
  /* border: 2px solid #333; */
  height: 200px;
  width: 200px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
  /* margin-bottom: 5px; */
}

.info {
  /* background: #C7D8D0; */
  color: #000;
  padding: 10px 30px;
  /* height: 80px; */
}

.info h1 {
  font-family: 'Lobster Two', cursive;
  font-size: 16px;
}

.info h2 {
  font-family: 'Roboto', sans-serif;
  font-size: 12px;
}

 .image-box{
  background-color: #C7D8D0;
}
/* .price {
  display: flex;
} */

button {

  background-color: #C7D8D0;
  border: none;
  padding: 5px;
}

.auto {
  margin-left: auto;
}
</style>
