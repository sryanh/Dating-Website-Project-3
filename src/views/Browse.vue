<template>
  <div>
    <div class="pure-menu pure-menu-horizontal">
      <ul class="pure-menu-list">
        <li class="pure-menu-item"><a @click="select('Orem')" href="#" class="pure-menu-link">Orem</a></li>
        <li class="pure-menu-item"><a @click="select('Provo')" href="#" class="pure-menu-link">Provo</a></li>
        <li class="pure-menu-item"><a @click="select('Draper')" href="#" class="pure-menu-link">Draper</a></li>
        <li class="pure-menu-item"><a @click="select('Mona')" href="#" class="pure-menu-link">Mona</a></li>
      </ul>
    </div>
    <div class="pure-menu pure-menu-horizontal">
      <ul class="pure-menu-list">
        <li class="pure-menu-item"><a @click="select$('$0')" href="#" class="pure-menu-link">$0</a></li>
        <li class="pure-menu-item"><a @click="select$('$10')" href="#" class="pure-menu-link">$10</a></li>
        <li class="pure-menu-item"><a @click="select$('$15')" href="#" class="pure-menu-link">$15</a></li>
        <li class="pure-menu-item"><a @click="select$('$20')" href="#" class="pure-menu-link">$20</a></li>
        <li class="pure-menu-item"><a @click="select$('$30')" href="#" class="pure-menu-link">$30</a></li>
        <li class="pure-menu-item"><a @click="select$('$35')" href="#" class="pure-menu-link">$35</a></li>
      </ul>
    </div>
  <ProductList :products="products" />
  <ProductList :products="products$" />

</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Browse',
  components: {
    ProductList
  },
  data() {
    return {
      variable: '',
    }
  },
  computed: {
    products$() {
      return this.$root.$data.products.filter(product => product.price === this.variable);
    },
    products() {
      return this.$root.$data.products.filter(product => product.location === this.variable);
    }
  },
  methods: {
    select$(price) {
      this.variable = price;
    },
    select(location) {
      this.variable = location;
    }
  }
}
</script>

<style scoped>
.pure-menu-list {
  display: flex;
  justify-content: center;
}
</style>
