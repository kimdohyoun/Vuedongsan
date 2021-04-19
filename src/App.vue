<template>

<div>

  
<div class="black-bg" v-if="모달창열렸니 == true">
  <div class="white-bg">
    <h4>상세 페이지임</h4>
    <p>상세 페이지 내용 임 </p>
      <button  class="close-bt" @click="모달창열렸니 = false">닫기</button> 
  </div>
</div>





<div class="menu">
  <a v-for="작명 in 메뉴들" :key= "작명">{{작명}}</a>
</div>


<div v-for="(a,i) in 원룸들" :key="i">
   <img :src="원룸들[i].image" class="room-img">
        <h4>{{원룸들[i].title}}</h4>
 <p>{{원룸들[i].price}}원 </p>
<p>{{원룸들[i].content}}</p>
  </div>



</div>


  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <div>
 <img :src="원룸들[0].image" class="room-img">
     <h4 @click="모달창열렸니 = true">{{원룸들[0].title}}</h4>
  <p>{{원룸들[0].price}}원 </p>
  <button @click="신고수[0] ++">허위매물신고</button>  <span>신고수 : {{신고수[0]}}</span>
  </div>

<div>
  <img src="./assets/room1.jpg" class="room-img">
    <h4>{{products[1]}}</h4>
  <p>{{price2}}만원 </p>
    <button @click="신고수[1] ++">허위매물신고</button>  <span>신고수 : {{신고수[1]}}</span>
  </div>
   <div>
     <img src="./assets/room2.jpg" class="room-img">
     <h4>{{products[2]}}</h4>
  <p>{{price1}}만원 </p>
    <button @click="신고수[2] ++">허위매물신고</button>  <span>신고수 : {{신고수[2]}}</span>
  </div> -->

</template>

<script>
// <!-- // UI의 현재 상태를 데이터로 저장해둠
// // 데이터에 따라 UI 가 어떻게 보일지 작성 -->
// import apple from './assets/oneroom.js' 
// apple;
// import {apple, apple2} from './assets/oneroom.js'
// apple2;
// apple;
import data from './assets/oneroom'


export default {
  name: 'App',
  data(){
    return{
      원룸들: data,
      모달창열렸니 : false ,
      신고수 : [0,0,0],
      price : [80 ,70,50],
      products : ['역삼동 원룸','천호동원룸','마포구원룸'],
       메뉴들:['Home','Shop','about','AS'],
    }
  },
  methods: {
    increase(){
      this.신고수 += 1
    }
  },
  components: {
  }
}
</script>

<style>

body{
  margin  : 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
background: rgba(0,0,0,0.5);
position: fixed; padding: 20px;
}
.white-bg {
  width:100%; background: white;
  border-radius: 8px;
padding: 20px;
}

.close-bt{
  background: rgb(71, 127, 151);
  color: rgb(84, 72, 163);
  border: 1px;
}

.room-img{
  width: 100%;
  margin-top: 40px;
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
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;
}

</style>
