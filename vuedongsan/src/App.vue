<template>

  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button class="close-btn" @click="modal=false">닫기</button>
    </div>
  </div>



  <div class="menu">
    <a v-for="a in menus" :key="a">{{a}}</a>
  </div>



  <div v-for="i in oneRooms" :key="i">
    <img :src="i.image" class="room-img" alt="">
    <h4 @click="modal = true">{{i.title}}</h4>
    <p>{{i.price}} 만원</p>
  </div>
</template>

<script>

import data from "./assets/oneroom.js";

export default {
  name: 'App',
  data(){
    return{
      logo : "원룸샵",
      products : ['역삼동원룸', '천호동원룸','마포구원룸'],
      menus : ['Home','Products','About'],
      count:[0,0,0],
      modal : false,
      oneRooms : data,
    }
  },
  components: {
  },
  methods: {
    
  },
}
</script>

<style>
body{
  margin:0
}
div{
  box-sizing: border-box;
}
.black-bg{
  width:100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding:20px;
}
.white-bg{
  width:100%; background: white;
  border-radius: 8px;
  padding:20px;
} 
.close-btn{
  width:100px;
  height:30px;
  background-color: blueviolet;
  color:white;
  font-weight: bold;
}
.room-img{
  width:100%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.menu{
  background: darkslateblue;
  padding:15px;
  border-radius: 5px;
}
.menu a{
  color:white;
  padding:10px;
}
</style>
