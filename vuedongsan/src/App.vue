<template>
<!-- 데이터 바인딩 하는 이유
  : Vue의 실시간 자동 렌더링을 사용하기 위해
  data를 변경하면 HTML에도 실시간으로 반영됨
-->
<div>
  <div class="black-bg" v-if="모달창열렸니==true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열렸니=false">닫기</button>
    </div>

  </div>

  <div class="menu">
    <a v-for="(b,i) in lists" :key="b">{{i}}:{{b}}</a><!--a는 '메뉴들'의 값, i는 몇번째(i를 사용하지 않으면 에러가 난다)-->
   
  </div>
    <div v-for="(output,abc) in 원룸들" :key="output">
      <img :src="output.image" alt="">
      <p>room number : &lt;{{abc}}&gt;</p>
      <h4>room name : {{output.title}}</h4>
      <p>{{output.price}}</p>
    </div>
  <!-- <div v-for="room in temp" :key="room">
    <h4>{{room.name}}</h4>
    <p>{{room.prices}}만원</p>
  </div> -->
  <!-- <div>
    <img :src="원룸들[0].image" alt="룸0" class="room-img">
    <h4 @click="모달창열렸니=true">{{원룸들[0].title}}</h4>
    <p>{{원룸들[0].price}} 만원</p>
    <button @click="신고수[0]++">허위매물신고</button>
    <span>신고수1 : {{신고수[0]}}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" alt="룸1" class="room-img">
    <h4>{{products[1]}}</h4>
    <p>{{price[1]}} 만원</p>
    <button @click="신고수[1]++">신고합시다</button>
    <span>신고수2 : {{신고수[1]}}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" alt="룸2" class="room-img">
    <h4>{{products[2]}}</h4>
    <p>{{price[2]}} 만원</p>
    <button @click="신고수[2]++">신고합시다</button>
    <span>신고수3 : {{신고수[2]}}</span>
  </div> -->
 </div>
</template>

<script>
import data from './assets/oneroom.js';

export default {
  name: 'App',
  data(){
    return{
      //object 자료형
      price : [60/2,70,80],
      스타일1 : 'color : blue ',
      products : ['역삼동원룸','천호동원룸','마포구원룸'],
      lists : ['Home','Shop','About'],
      신고수 :[0,0,0],
      // temp : [
      //   {name : '역삼동원룸', prices : 60/2},
      //   {name : '천호동원룸', prices : 70},
      //   {name : '마포구원룸', prices : 80},
      //   ],
      모달창열렸니 : false, // 모달창 현재상태 저장
      원룸들 : data,
    }
  },
  methods: {
   
  },
  components: {
  }
}

</script>

<style>
body{
  margin : 0;
}
div { 
  box-sizing :border-box;
}
.black-bg{
  width:100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding:20px;
}
.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}


.room-img{
  width:30%;
  margin-top: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}
.menu{
  background :darkslateblue;
  padding : 15px;
  border-radius : 5px;
}

.menu a{
  color : white;
  padding :10px;
}

</style>
