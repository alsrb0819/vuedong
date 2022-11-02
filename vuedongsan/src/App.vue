<template>

  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>추가 상품증정</h4>
      <p></p>
      <button @click="모달창열렸니 = false">close</button>
    </div>
  </div>


  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{a}}</a>
  </div>

  <div v-for="(m,i) in 원룸들" :key="i">
    <img :src="원룸들[i].image" class="room-img" @click="모달창열렸니 = true"/>
    <h4>{{원룸들[i].title}}</h4>
    <p>{{원룸들[i].price}} 만원</p>
    <button @click="신고수[i]++"><img src="./img/like.webp" class="btnimg"></button> <span>좋아요 : {{신고수[i]}}</span>
  </div>
</template>

<script>
import  data  from "./data";

export default {
  name: 'App',
  data(){     // data를 저장하는 곳
    return{
      원룸들 : data,
      products : ['역산동원룸' , '천호동원룸' , '마포구원룸'],
      메뉴들 : ['Home' , 'Shop' , 'About'],
      신고수 : [0,0,0],
      모달창열렸니 : false,
    }
  },

  methods : {
    
  },
  components: {
    
  }
}
</script>

<style>
body{
  margin : 0
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}

.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img {
  width:100%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale; 
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color:white;
  padding: 10px;
}

.btnimg {
  width: 20px;
}
</style>
