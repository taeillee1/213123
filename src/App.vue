<template>
  <div class="menu">
    <a v-for="imenu in 메뉴들" :key="imenu">{{imenu}}</a>
    <!-- <a v-for="(imenu,i) in 메뉴들" :key="i">{{i}}</a> -->
  </div>
    <!-- <h4 class="red" :style="스타일">XX {{logo}}</h4>  -->
  
  <div v-for="(product,i) in product" :key="i" class="sub">
    <h3>{{product}}</h3>
    <a>{{가격들[i]}}</a>
  </div>
</template>

<script>

export default {
  name: 'App',

  data(){ //데이터를 저장하는 곳
    return {
      price1 : 60,
      logo : '원룸shop',
      스타일 : "color : red",
      메뉴들 : ['Home','Shop','About','Cart'],
      가격들 : ['70','90','30'],
      product : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
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
  
}
.red{
  font-size: 60px;
}
.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  font-size: 30px;
  padding: 10px;
}
.sub{
  font-size: 20px;
}
</style>
