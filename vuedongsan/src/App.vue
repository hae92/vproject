<template>
  <div>
    <div class="menu">
      <a v-for="item, index in Menu" :key="index">{{Menu[index]}}</a>
    </div>

    <img alt="Vue logo" src="./assets/logo.png" width="200">
    <h4>{{LogoTitle}}</h4>

    <div v-for="product, index in Products" :key="index">
      <h4 :style=myStyle01>{{Products[index].Name}}</h4>
      <p>{{Products[index].Price}} 만원</p>
    </div>
  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      LogoTitle : 'One Room Shop',
      Menu : ['Home', 'Products', 'About'],
      
      myStyle01 : 'color : blue',      

      Products : [
        {
          Name : '역삼동원룸',
          Price : 6000,
        },
        {
          Name : '천호동원룸',
          Price : 7000,
        },
        {
          Name : '마포구원룸',
          Price : 8000,
        },
      ]
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
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
