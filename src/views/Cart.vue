<template>
<div>
  <div class="wrapper">
    <form class="pure-form">
    </form>
  </div>
  <div class="CartMessage">
    <!-- put vif here and velse in another div-->
    <div class="ifStatement" v-if="this.$root.$data.cart.length === 0">Nothing Here!</div>
    <div class="ElseStatment" v-else>
      <ul v-for="product in this.$root.$data.cart" :key="product.id">
        <div class='dateHeart'><button v-on:click="RemoveProduct(product)">
          <div class= 'name'>
              {{product.name}}
            </div>
          <div class="image">
            <img :src="'/images/products/'+product.image">
          </div>
          <p> {{product.description}} </p>
          <i class="fas fa-times"></i></button>
          <!-- add remove button here with function  *** IF AN ISSUE COMES v-bind:for product-->
        </div>
      </ul>
    </div>
  </div>
</div>
</template>

<script>
// import CartList from "../components/CartList.vue"
export default {
  name: 'Home',
  // components: {
  //   CartList
  // },
  data() {
    return {
      searchText: '',
    }
  },
  methods: {
    RemoveProduct(product) {
      this.$root.$data.cart.splice(this.$root.$data.cart.indexOf(product), 1);
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

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}

.name {
font-size: 25px;
}

button {
  background-color: #DFBBB6;
  padding: 5px;
  font-size: 20px;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}

.ifStatement {
  text-align: center;
}


img {
  height: 300px;
  width: 300px;
  object-fit: cover;
}

.ElseStatment {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

</style>
