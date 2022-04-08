<template>
  <div class="menu">
    <a v-for="imenu in 메뉴들" :key="imenu">{{imenu}}</a>
    <!-- <a v-for="(imenu,i) in 메뉴들" :key="i">{{i}}</a> -->
  </div>
    <!-- <h4 class="red" :style="스타일">XX {{logo}}</h4>  -->

  <div>
    <h1>{{logo}}</h1>
    <input type="text" v-model="logo"/>
    <p v-if="logo.length>9">너무길어요</p>
    <button>검색</button>
    <button v-on:click="addItem">추가버튼</button>
    <button v-on:click="popItem">삭제버튼</button>
  </div>
  
  
  <div v-for="(product,i) in products" :key="i" class="sub">
    <h3>{{product}}</h3>
    <a>{{가격들[i]}}</a>&nbsp;
    <button class="btn" type="button" @click="getData">{{i}}</button>
    <button class="setbtn" type="button" @click="setData">{{i}}</button>
  </div>

  <div>
    <ul>
      <li v-for="(user,index) in users" :key="index" style="text-align : left">
        이름은 {{user.name}}&emsp; 직업은 {{user.job}}&emsp; 성별은 {{user.gender}}
      </li>
    </ul>
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
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
      users: [
        { name : 'scalper', job : 'backend-developer', gender: 'male' },
        { name : 'john', job : 'designer', gender: 'female' },
        { name : '철수', job : 'frontend-developer', gender: 'male' }
      ]
    } 
  },
  methods: {
    getData(){
      alert("버튼입니다~");
    },
    setData(){
      this.products[0]="1111121";
    },
    addItem(){
      this.products.push(this.logo)
    },
    popItem(){
      this.products.pop()
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
.btn{
  background: rgb(250, 147, 147);
  padding: 4px;
  margin: 10px;
  width: 10%;
  font-size: 20px;
}
.setbtn{
  background: rgb(147, 250, 190);
  padding: 4px;
  width: 10%;
  font-size: 20px;
}
</style>
