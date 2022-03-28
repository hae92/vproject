<template>
  <div>
    <div class="black-bg" v-if="Modal">
      <div class="white-bg">
        <h4>{{Products[SelectedRoom].title}}</h4>
        <p>{{Products[SelectedRoom].content}}</p>
        <button @click="DisplayModel(0, false)">Close</button>
      </div>
    </div>

    <div class="menu">
      <a v-for="item, index in Menu" :key="index">{{Menu[index]}}</a>
    </div>

    <img alt="Vue logo" src="./assets/logo.png" width="200">
    <h4>{{LogoTitle}}</h4>

    <div v-for="product, index in Products" :key="index">
      <img :src="Products[index].image" class="room-img">
      <h4 @click="DisplayModel(index, true)" :style=MyStyle>{{Products[index].title}}</h4>
      <p>{{Products[index].price}} 만원</p>
      <button @click="Increase(index)">허위매물신고</button> <span>신고수 : {{Products[index].count}}</span>
    </div>
  </div>
</template>

<script>

import onerooms from './assets/onerooms.js';

export default {
  name: 'App',
  data() {
    return {
      LogoTitle : 'One Room Shop',
      MyStyle : 'color : green',
      Menu : ['Home', 'Products', 'About'],
      Modal : false,
      SelectedRoom : 0,
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
    }
  },
  components: {
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
