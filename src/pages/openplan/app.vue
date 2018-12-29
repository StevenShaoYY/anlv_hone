<template>
  <div id="app">
    <top-bar :active="'4-2'"></top-bar>
    <div :height="topHeight">
        <img class="top-img" src="../../assets/openplan.png" alt="">
    </div>
    <section class="main">
      <div class="main-c">
        <h3 class="title">接入说明</h3>
        <div class="content2">
          <img class="sed-img" src="../../assets/jieru.png" alt="">
        </div>
      </div>
      <div class="main-c bottom-last" id="miao2">
        <h3 class="title">开发手册</h3>
        <div class="content">
          <a href="./doc/安旅盒子设备接入接口设计.pdf" download class="box-item">
            <h4>人证核验设备对接文档</h4>
            <p>介绍人证核验设备如何与开放平台对接，使设备厂商实现人证核验设备和人证核验功能接入。</p>
          </a>
          <a href="./doc/安旅盒子服务接口设计-自助机.pdf" download class="box-item">
            <h4>自助机服务对接文档</h4>
            <p>介绍自助机如何与开放平台对接，使自助机可以完成旅客入住登记功能。</p>
          </a>
          <a href="./doc/安旅盒子服务接口设计-PMS.pdf" download class="box-item">
            <h4>PMS服务对接文档</h4>
            <p>介绍PMS如何与开放平台对接，使PMS可以实现一次性录入，旅馆基础信息同步功能。</p>
          </a>
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
    bottom
  },
  data() {
    return {
      topHeight: '0px',
      screenWidth: document.body.clientWidth
    }
  },
  created() {
    this.topHeight = document.body.clientWidth/5 -10 + 'px'
  },
  mounted() {
    window.onresize = () => {
        return (() => {
            window.screenWidth = document.body.clientWidth
            this.screenWidth = window.screenWidth
        })()
    }
  },
  watch: {
      screenWidth (val) {
        this.topHeight = val/3.6 -10 + 'px'
      }
  },
  methods: {
    adjuest() {
      this.topHeight = document.body.clientWidth/3.6 -10 + 'px'
    },
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
@media screen and (max-width:1200px){
  .main {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: calc(100vh - 547px);
  }
  .main-c{
    padding: 0 20px;
}
.content .box-item{
  width: 30%;
  height: 161px;
  border:1px solid rgba(204, 204, 204, 1);
  cursor: pointer;
}
 
}
@media screen and (min-width:1200px){
  .main {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .main-c{
    width: 1200px;
    
  }
  .content .box-item{
  width: 390px;
  height: 161px;
  border:1px solid rgba(204, 204, 204, 1);
  cursor: pointer;
}
}

.top-img{
  width:100%;
}

.bottom-last {
  margin-bottom: 80px;
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
  justify-content: center;
  margin-top: 30px;
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
