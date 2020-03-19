<template>
<div id="app">
  <div id="menu">
    <div id="brand">
        <p>Date Provo</p>
    </div>
    <div id="side">
      <router-link to="/">
        <div class="menu-item browse">
        <p><i class="fas fa-home"></i> Home</p>
      </div>
      </router-link>
      <router-link to="/browse">
        <div class="menu-item browse">
          <p><i class="fas fa-fire"></i> Filter</p>
          <!-- Change name here:)  -->
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <p><i class="fas fa-clipboard-list"></i> Wish List</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
  <br>
  <div class= "page">
     <div class="footer">
       <p>Savannah Herbon -
         <a href='https://github.com/sryanh/Dating-Website-Project-3'>GitHub</a>
          - Kirsten Kerksiek</p></div>
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
  /* margin: 50px 100px; */

}
/* #app{
  background-color: #F4E8D2 !important;
} */
#menu {
  padding-top: 25px;
  background-color: #DD7864;
  color: white;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: white;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand  {
  /* padding-top: 20px; */
  /* padding-bottom: 25px; */
  font-size: 4.5rem;
  font-family: 'Lobster', cursive;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: right;
  font-family: 'Roboto', sans-serif !important;
}

#side img {
  width: 50px;
}
.menu-item {
  display: flex;
  flex-direction: column;
  font-family: 'Roboto', sans-serif !important;
}
.footer{
    
    font-family: 'Lobster', cursive;
    color: white;
}
.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}
.page{
  height: 50px;
  background-color: #DD7864 !important;
  font-size: 20px;
  text-align: center;
}
</style>
