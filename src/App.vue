<template>
<div id="app">
  <div id="menu">
    <div id="brand">
        <p>- Date Provo -</p>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse">
          <i class="fas fa-grin-hearts"></i>
          <p>Browse</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <img src="/images/love.png">
          <p>{{numberOfItems}} Items</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
  <br>
  <div class= "page">
     <div class="footer"><a href='https://github.com/BYU-CS-260-Winter-2020/lab-3b-grocery-store-sryanh'>GitHub</a></div>
  </div>
</div>

</template>

<script>
export default{
  computed:{
    numberOfItems()
    {
      return this.$root.$data.cart.length;
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;

}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: #B84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: right;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}
.page{
  height: 50px;
  background-color: #FFE5CE !important;
  font-size: 20px;
  text-align: center;
}
</style>
