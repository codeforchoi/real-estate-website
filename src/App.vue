<template>  
  <div class="black-bg" v-if="isOpenModal == true">
    <div class="white-bg"> 
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="isOpenModal = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(menu_name, i) in menu" :key="menu_name">{{ i+1 }} {{ menu_name }}</a>    
  </div>
  
  <div>    
    <img src="./assets/room0.jpg" class="room-img">
    <h4 @click="isOpenModal = true">{{ onerooms[0].title }}</h4>
    <p>{{ onerooms[0].price }}원</p>
    <button @click="count[0]++">허위매물신고</button> 
    <span>신고수 : {{count[0]}}</span>
  </div>

  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4 @click="isOpenModal = true">{{ onerooms[1].title }}</h4>
    <p>{{ onerooms[1].price }}원</p>
    <button @click="count[1]++">허위매물신고</button> <span>신고수 : {{count[1]}}</span>
  </div>

  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4 @click="isOpenModal = true">{{ onerooms[2].title }}</h4>
    <p>{{ onerooms[2].price }}원</p>
    <button @click="count[2]++">허위매물신고</button> <span>신고수 : {{count[2]}}</span>
  </div>

  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4 @click="isOpenModal = true">{{ onerooms[3].title }}</h4>
    <p>{{ onerooms[3].price }}원</p>
    <button @click="count[3]++">허위매물신고</button> <span>신고수 : {{count[3]}}</span>
  </div>

  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4 @click="isOpenModal = true">{{ onerooms[4].title }}</h4>
    <p>{{ onerooms[4].price }}원</p>
    <button @click="count[4]++">허위매물신고</button> <span>신고수 : {{count[4]}}</span>
  </div>

  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4 @click="isOpenModal = true">{{ onerooms[5].title }}</h4>
    <p>{{ onerooms[5].price }}원</p>
    <button @click="count[5]++">허위매물신고</button> <span>신고수 : {{count[5]}}</span>
  </div>
</template>

<script>

import data from './model/data.js';

export default {
  name: 'App',
  data() {
    return { 
      isOpenModal : false,
      count : [0, 0, 0, 0, 0, 0], 
      menu : ['Home', 'Shop', 'About'],     
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
      onerooms : data,
    }
  },
  methods : {
    increase() {
      this.count[0]++;      
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

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

.body {
  margin : 0;
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

.white-bg {
  width: 100%; 
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>