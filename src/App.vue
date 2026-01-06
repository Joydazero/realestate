
<template>
  <div class="black-bg" v-if="modalState == true" @click="modalState = false">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
    </div>
  </div>

  <div class="menu">
    <a v-for="a in menus" :key="a">{{ a }}</a>
  </div>
  <img src="./assets/logo.svg" alt="Vue logo" class="vue-logo" />
  <div>
    <div v-for="(item,i) in other" :key="i">
      <img :src="item.imgs" alt="" class="room-img" @click="modalState = true">
      <h4 >{{ item.name }}</h4>
      <p>{{ item.price }}</p>    
      <button @click="increase(i)">허위 매물 신고</button><span>신고수 : {{ item.complaintcount }}</span>      
    </div>
    
  </div>
</template>
<script >
  
  export default  {
    name: 'App',
    data(){
      return {
        // 데이터 보관함
        complaintCount :0,
        menus : ['Home','Shop','About'],
        other : [{'name':'역삼동 원룸','price':'50만원', 'complaintcount' : 0, 'imgs': '/src/assets/room0.jpg'},{'name':'천호동 원룸','price':'60만원', 'complaintcount' : 0, 'imgs': '/src/assets/room1.jpg'},{'name':'마포구 원룸','price':'70만원', 'complaintcount' : 0, 'imgs': '/src/assets/room2.jpg'}],       
        modalState : false
      }
    },
    methods : {
      increase(index){
        this.other[index].complaintcount ++;
      },
      decrease(index){
        this.other[index].complaintcount --;
      }
    }
    // components : {

    // }
  };          
</script>
<style>
  body{
    margin:0;
    padding:0;
  }
  #app{
    font-family: Avenirm, Helvetica , Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale; 
    text-align:center;
    color:#2c3e50;
  }
  div{
    box-sizing:border-box;
  }
  .room-img{ width:100%; margin-top:40px;}
  .vue-logo{
    margin-top:30px;
    max-width:150px;
  }
  .menu {
    background:darkslateblue;
    padding:15px;
    border-radius:5px; 
    }
  .menu a{
    color: white;
    padding:10px;
  }
  .black-bg{
    width:100%;
    height:100%;
    background:rgba(0,0,0,0.5);
    position:fixed;
    padding:20px;
  }
  .white-bg{
    width:100%;
    background:#fff;
    border-radius:8px;
    padding:20px;
  }
</style>
