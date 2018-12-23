<template>
  <div id="app">
    <top-bar :active="'3-2'"></top-bar>
    <div :height="topHeight">
        <img class="top-img" src="../../assets/anplan.png" alt="">
    </div>
    <div class="main bottom-last">
      <div class="jieshao-content">安旅科技以易公安安全终端为基础，以互联网为通道，围绕旅业治安登记管理核心业务，连接身份证阅读仪、扫描仪、证件通等外设，打造了易公安旅业治安登记方案。安旅科技深耕旅客前台交互场景设计、旅客人像识别比对、扫描证件文字识别,从而提升了旅客入住体验、简化了前台登记流程、提高了采集数据质量。</div>
      <div class="item-content">
        <div class="item-header">
          <div class="title-container">
            <div class="line"></div>
            <h3 class="title">安全终端开放服务接入方案</h3>
            <div class="line"></div>
          </div>
        </div>
        <div class="item-main" >
          <div class="js-img">
            <img src="../../assets/aqzdjrfa.png" alt="">
          </div>
          <div class="it-text">
            <div class="text-header">适用场景</div>
            <div class="item-main-text first">智能化、无人化酒店</div>
            <div class="text-header">主要功能</div>
            <div class="item-main-text first">人证核验</div>
            <div class="item-main-text">自助机入住登记</div>
            <div class="item-main-text">PMS入住登记</div>
          </div>
        </div>
      </div>
    </div>
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
    this.topHeight = document.body.clientWidth/3.6 -10 + 'px'
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
.main {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.jieshao-content { 
  width: 1200px;
  margin: 80px 0 0 0;
}
.item-content {
  width: 1200px;
  display:flex;
  flex-direction: column;
  align-items: center;
  margin-top: 100px;
}
.title-container{
  display: flex;

}
.title-container .line{
  height: 48px;
  width: 160px;
  border-bottom: 2px solid #FF961A;
}
.title-container .title{
  font-size:48px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(51,51,51,1);
  padding: 0 20px;
}
.header-text {
  font-size: 20px;
  text-align: center;
}
.item-main{
  display: flex;
  margin-top: 80px;
}
.item-main .it-text {
  margin-left: 150px;
}
.item-main .it-text .text-header {
  width:206px;
  height:32px;
  margin-top: 20px;
  text-align: center;
  line-height: 32px;
  font-size:20px;
  background:rgba(204,204,204,1);
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(255,255,255,1);
}
.item-main-text {
  font-size: 16px;
  line-height: 30px;
}
.js-img {
  width: 870px;
  height: 392px;
  text-align: right;
}
.first{
  margin-top: 20px;
}
.bottom-last {
  margin-bottom: 80px;
}
</style>
