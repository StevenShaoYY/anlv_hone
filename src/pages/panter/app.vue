<template>
  <div id="app">
    <top-bar :active="'6'"></top-bar>
     <div >
        <img class="top-img" src="../../assets/panter.png" alt="">
    </div>
    <section class="main">
      <div class="main-c">
        <h3 class="title">安旅合作伙伴</h3>
        <div class="content2">
          <p>安旅科技以合作共赢的姿态，积极主动地与优秀的企业达成合作关系，致力为酒店和旅客带来更加安全、便捷、高效、稳定的入住登记系统。</p>
        </div>
        <div class="img-container">
          <img src="../../assets/panter-pic1.png" alt="">
          <img src="../../assets/panter-pic2.png" alt="">
          <img src="../../assets/panter-pic3.png" alt="">
          <img src="../../assets/panter-pic4.png" alt="">
          <img class="last-img" src="../../assets/panter-pic5.png" alt="">
        </div>
      </div>
    </section>
    <bottom></bottom>
  </div>
</template>

<script>
import topBar from '../../components/header.vue'
import bottom from '../../components/bottom.vue'
export default {
  components: {
    topBar,
    bottom,
  },
  data() {
    return {
     
    }
  },
  created() {
  },
  mounted() {
    
  },
  methods: {
    gogogo() {
      location.assign('../customer/home.html')
    },
    tototo() {
      location.assign('../user/login.html')
    }
  }
}
</script>

<style lang="postcss">
.main {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.top-img{
  width:100%;
}
.main-c{
  width: 1200px;
  
}
.bottom-last {
  margin-bottom: 80px;
}
.img-container img + img{
  margin-left: 10px;
}
.last-img {
  margin-left: 0px !important;
  margin-top: 10px;
  margin-bottom: 100px;
}
.title{
  margin-top: 50px;
  font-size:30px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(0,0,0,1);
}
.content {
  display: flex;
  justify-content: space-between;
  margin-top: 30px;
}
.content2 {
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-top: 30px;
  font-size: 16px;
  margin-bottom: 100px;
}
.content .box-item{
  width: 390px;
  height: 161px;
  border:1px solid rgba(204, 204, 204, 1)
}
.box-item p{
  font-size:16px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(51,51,51,1);
  margin: 20px 15px;
}
.box-item h4{
  font-size:24px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(0,0,0,1);
  line-height:30px;
  margin: 20px 15px;
}
</style>
