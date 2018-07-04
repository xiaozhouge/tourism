<template>
  <div id="app">
    <div class="header">
      <img src="./assets/images/logo.png"  title="logo">
    </div>
    <div class="content">
      <router-view/>
    </div>
    <ul class="menu">
      <li @click="selItem('homeSel')" 
          :style="{color:!homeSel?'green':'#000'}">
        <img :src="homeSel?homeSvg:green_homeSvg" alt="home-icon">
        主页
      </li>
      <li @click="selItem('guanyuSel')"
          :style="{color:!guanyuSel?'green':'#000'}">
        <img :src="guanyuSel?guanyuSvg:green_guanyuSvg" alt="">
        关于
      </li>
      <li @click="selItem('personSel')"
          :style="{color:!personSel?'green':'#000'}">
        <img :src="personSel?personSvg:green_personSvg" alt="">
        我的
      </li>
    </ul>
  </div>
</template>

<script>
import homeSvg from "./assets/images/home.svg"
import green_homeSvg from "./assets/images/green_home.svg"
import guanyuSvg from "./assets/images/guanyu.svg"
import green_guanyuSvg from "./assets/images/green_guanyu.svg"
import personSvg from "./assets/images/person.svg"
import green_personSvg from "./assets/images/green_person.svg"
export default {
  name: 'App',
  data(){
    return{
      homeSvg:homeSvg,
      green_homeSvg:green_homeSvg,
      homeSel:false,
      guanyuSvg:guanyuSvg,
      green_guanyuSvg:green_guanyuSvg,
      guanyuSel:true,
      personSvg:personSvg,
      green_personSvg:green_personSvg,
      personSel:true,
    }
  },
  methods:{
    // 
    selItem(v){
      if (v=="homeSel") {
        this.homeSel=false;
        this.guanyuSel=true;
        this.personSel=true;
      }else if(v=="guanyuSel"){
        this.homeSel=true;
        this.guanyuSel=false;
        this.personSel=true;
      }else{
        this.homeSel=true;
        this.guanyuSel=true;
        this.personSel=false;
      }
      
    }
  }
}
</script>

<style scoped lang="less">
  #app{
     height: 100%;
    .header{
      background: green;
      height: 64px;
      display: flex;
      align-items: center;
      img{
        width:35px;
        height: 35px;
        margin-left: 10px;
      }
    }
    .content{
      height: calc(~'100% - 114px');
    }
    .menu{
      height: 50px;
      width: 100%;
      display: flex;
      border-top: 1px solid #ccc;
      justify-content: space-around;
      li{
        display:flex;
        flex: 1;
        align-items: center;
        border-left: 1px solid #ccc;
        flex-direction: column;
        font-size: 12px;
        justify-content: space-around;
        font-family: Microsoft YaHei;
        img{
          padding-top:5px;
          width: 24px;
          height: 24px;
        }
      }
      li:nth-child(1){
        border-left: 0;
      }
    }
  }
  
</style>
