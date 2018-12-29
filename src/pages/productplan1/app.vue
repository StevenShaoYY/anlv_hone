<template>
  <div id="app">
    <top-bar :active="'2'"></top-bar>
    <div :height="topHeight">
      <img class="top-img" src="../../assets/productplan1.png" alt="">
    </div>
    <div class="main">
      <div class="item-content">
        <div class="item-header">
          <div class="title-container">
            <h3 class="title">互联网直连，无VPND费用，易接入</h3>
          </div>
          <div class="header-text" >通过互联网安全加密通道将住宿登记信息送入公安网。</div>
        </div>
        <div class="item-main" >
          <div class="js-img">
            <img src="../../assets/tu1.png" alt="">
          </div>
        </div>
      </div>
      <div class="item-content">
        <div class="item-header">
          <div class="title-container">
            <h3 class="title">内置登记客户端，满足治安登记需求</h3>
          </div>
          <div class="header-text" >易公安内置登记客户端，实现了旅客登记、访客登记、无证登记等治安登记需求。</div>
        </div>
        <div class="item-main" >
          <img src="../../assets/tu2.png" class="js-img" alt="">
        </div>
      </div>
      <div class="item-content">
        <div class="item-header">
          <div class="title-container">
            <h3 class="title">支持人证核验，精准对比防止作假</h3>
          </div>
          <div class="header-text" >易公安支持人证核验设备接入，过快速抓拍人脸并与身份证图像信息进行精准比对，从而辨别持证人与证件是否为同一人。</div>
        </div>
        <div class="item-main" >
          <img src="../../assets/tu3.png" class="js-img" alt="">
        </div>
      </div>
      <div class="item-content">
        <div class="item-header">
          <div class="title-container">
            <h3 class="title">开放服务接入，助力未来酒店</h3>
          </div>
          <div class="header-text" >易公安通过开放服务接口与酒店自助机、PMS数据互通，实现一次性录入登记。</div>
        </div>
        <div class="item-main" >
          <img src="../../assets/tu4.png" class="js-img" alt="">
        </div>
      </div>
      <div class="item-content bottom-last">
        <div class="item-header">
          <div class="title-container">
            <h3 class="title">技术参数</h3>
          </div>
        </div>
        <div class="item-main" >
          <div class="text-container">
            <div class="yigongan-pic"></div>
            <div class="right-container">
              <div class="guige-con">
                <p class="p1">处理器</p>
                <p>4核心2GHz</p>
              </div>
              <div class="guige-con">
                <p class="p1">内存</p>
                <p>1GB&nbspDDR3/3L</p>
              </div>
              <div class="guige-con">
                <p class="p1">存储</p>
                <p>4GB/8GB EMMC</p>
              </div>
              <div class="guige-con">
                <p class="p1">电源功耗</p>
                <p>DC 12V ; 12W</p>
              </div>
              <div class="guige-con">
                <p class="p1">网络参数</p>
                <p>以太网10M/100M自适应 </p>
              </div>
              <div class="guige-con">
                <p class="p1">设备接口</p>
                <p>HDMI*1/USB2.0*4</p>
              </div>
              <div class="guige-con">
                <p class="p1">设备尺寸</p>
                <p>186*220*68(mm)</p>
              </div>
              <div class="guige-con">
                <p class="p1">设备重量</p>
                <p>500g</p>
              </div>
            </div>
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
@media screen and (max-width:1200px){
  .jieshao-content { 
    padding: 0 20px;
    margin: 80px 0 0 0;
  }
  .item-content {
  display:flex;
    padding: 0 20px;
  flex-direction: column;
  align-items: center;
  margin-top: 100px;
}
}
@media screen and (min-width:1200px){
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
}
.top-img{
  width:100%;
}
.main {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}


.title-container{
  display: flex;

}
.item-header{
  display: flex;
  flex-direction: column;
  align-items: center;
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
  margin-top: 20px;
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
  text-align: right;
}
.first{
  margin-top: 20px;
}
.bottom-last {
  margin-bottom: 80px;
}
.text-container {
  display: flex;
}
.right-container {
  width: 500px;
  display: flex;
  margin-left: 100px;
  flex-direction: column;
  justify-content: flex-start;
}
.suzhu-pic{
  width: 350px;
  height: 300px;
  background:transparent url('../../assets/proicon.png') no-repeat;
  background-position:-490px -184px;
}
.yigongan-pic{
  width: 300px;
  height: 300px;
  background:transparent url('../../assets/proicon.png') no-repeat;
  background-position:-100px -166px;
}
.kuailu-pic{
  width: 300px;
  height: 300px;
  background:transparent url('../../assets/proicon.png') no-repeat;
  background-position:-921px -176px;
}
.guige-con{
font-size:16px;
font-family:MicrosoftYaHei;
font-weight:400;
color:rgba(102,102,102,1);
display: flex;
line-height:50px;
border-bottom: 1px solid #cccccc
}
.guige-con .p1 {
width: 90px;
}
</style>
