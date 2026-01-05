
<template>
  <div class="menu">
    <a v-for="a in menus" :key="a">{{ a }}</a>
  </div>
  <img src="./assets/logo.svg" alt="Vue logo" class="vue-logo" />
  <div>
    <div v-for="(item,i) in other" :key="i">
      <h4>{{ item.name }}</h4>
      <p>{{ item.price }}</p>    
    </div>
    <button @click="increase()">허위 매물 신고</button><span>신고수 : {{ complaintCount }}</span>
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
        other : [{'name':'역삼동 원룸','price':'50만원'},{'name':'천호동 원룸','price':'60만원'},{'name':'마포구 원룸','price':'70만원'}]
        
      }
    },
    methods : {
      increase(){
        this.complaintCount +=1;
      },
      decrease(){
        this.complaintCount -=1;
      }
    }
    // components : {

    // }
  };          
</script>
<style>
  #app{
    font-family: Avenirm, Helvetica , Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale; 
    text-align:center;
    color:#2c3e50;
  }
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

</style>
