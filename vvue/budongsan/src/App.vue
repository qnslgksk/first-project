<template>
  <ul class="menu-list">
    <li v-for="(list,i) in menu" :key="i"><a href="">{{ list }}</a></li>
  </ul>
  
  <div class="modal-bg" v-if="modal == true">
    <div class="modal">
      <h4>모달 타이틀</h4>
      <p>모달 상세 내용<br>블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라블라</p>
      <button class="close" @click="modal = false">닫기</button>
    </div>
    

  </div>


  <ul class="item-list">
    <li v-for="(bang,i) in item" :key="i">
      <a href="">
        <div>
          <img class="room-img" :src="room[i].image" alt="">
          <h4 @click="modal = true">{{room[i].title}}</h4>
          <p>{{room[i].price}}</p>
          <button>허위매물신고</button> <span>신고수 : {{ 신고수[0] }}</span>
        </div>
      </a>
    </li>
  </ul>
</template>

<script>
import data from './assets/room.js';

export default {
  name: 'App',
  data(){
    return {
      room : data,
      modal : false,
      신고수 : [0, 0, 0],
      menu : ['Home', 'Shop', 'About'],
      item : ['역삼동원룸', '압구정원룸', '천호동원룸'],
    }
  },
  methods : {
    increase(){
      this.신고수 += 1;
    }
  },

  components: {
  }
}
</script>

<style>
body{margin: 0;}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu-list{
  margin: 0;
  padding: 0;
  list-style: none;
  /* normalize */
  display: flex;
  justify-content: center;
  align-items: center;
  background: darkslategray;
  padding: 15px;
  border-radius:5px;
}

.menu-list a{
  text-decoration: none;
  color: #fff;
  padding: 10px;
}

.item-list{
  margin: 0;
  padding: 0;
  list-style: none;
}

.item-list a{
  text-decoration: none;
  color:#333;
}

.room-img{
  width: 100%;
  margin-top: 40px;
}

.modal-bg{
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  display: flex; 
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
  padding: 20px;
  background: rgba(0,0,0,.5);
}

.modal{
  width: 50vw;
  padding: 20px;
  border-radius: 8px;
  background:#fff;
}

.modal p{overflow-y:scroll;
height: 300px;}

.close{}
</style>
