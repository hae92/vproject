<template>
  <div>
    <ModalView :Products="Products" :SelectedRoom="SelectedRoom" :Modal="Modal" :DisplayModel="DisplayModel"></ModalView>

    <div class="menu">
      <a v-for="item, index in Menu" :key="index">{{Menu[index]}}</a>
    </div>
    <Discount v-if="true"></Discount>

    <img alt="Vue logo" src="./assets/logo.png" width="200">
    <h4>{{LogoTitle}}</h4>

    <div v-for="product, index in Products" :key="index">
      <Card @click="DisplayModel(index, true)" :product="product"></Card>
    </div>    
  </div>
</template>

<script>

import onerooms from './assets/onerooms.js';
import Discount from './components/Discount.vue'
import ModalView from './components/ModelView.vue'
import Card from './components/Card.vue'

export default {
  name: 'App',
  data() {
    return {
      LogoTitle : 'One Room Shop',
      MyStyle : 'color : green',
      Menu : ['Home', 'Products', 'About'],
      Products : onerooms,
    }
  },
  methods: {
    Increase(index) {
      this.Products[index].count++
    },
    DisplayModel(index, show) {
      this.SelectedRoom = index
      this.Modal = show
      this.Products[index].count++
      this.Products[index].count--
    },
    Change() {

    }

  },
  components: {
   Discount : Discount, 
   ModalView : ModalView,
   Card : Card,
  }
}
</script>


<style>
body {
  margin : 0
}
div {
  box-sizing : border-box;
}

.black-bg {
  width : 100%; 
  height : 100%;
  background: rgba(0, 0, 0, 0.5);
  position : fixed;
  padding : 20px;
}
.white-bg {
  width : 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.room-img {
  width : 100%;
  margin-top:40px;
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color : white;
  padding: 10px;
}
</style>
