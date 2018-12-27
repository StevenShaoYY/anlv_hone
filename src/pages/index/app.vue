<template>
  <div id="app">
    <top-bar :active="'1'"></top-bar>
    <el-carousel :height="topHeight">
      <el-carousel-item>
        <!-- <image class="img" src="../assets/herderpic.png"/> -->
        <img class="top-img" src="../../assets/herderpic1.png" alt="">
      </el-carousel-item>
      <el-carousel-item>
        <!-- <image class="img" src="../assets/herderpic.png"/> -->
        <img class="top-img" src="../../assets/herderpic2.png" alt="">
      </el-carousel-item>
      <el-carousel-item>
        <!-- <image class="img" src="../assets/herderpic.png"/> -->
        <img class="top-img" src="../../assets/herderpic3.png" alt="">
      </el-carousel-item>
      <el-carousel-item>
        <!-- <image class="img" src="../assets/herderpic.png"/> -->
        <img class="top-img" src="../../assets/herderpic4.png" alt="">
      </el-carousel-item>
    </el-carousel>
    <section class="content-container">
      <div class="img1">
        <!-- <img  src="../../assets/sy_t1.png" alt=""> -->
      </div>
      <div class="text-container" :class="{'run-text-1': runFlag}">
        <h3>旅业治安登记互联网方案</h3>
        <p class="content">安旅科技以易公安安全终端为基础，以互联网为通道，围绕旅业治安登记管理核心业务，连接身份证阅读仪、扫描仪、证件通等外设，打造了易公安旅业治安登记方案。安旅科技深耕旅客前台交互场景设计、旅客人像识别比对、扫描证件文字识别,从而提升了旅客入住体验、简化了前台登记流程、提高了采集数据质量。</p>
        <div class="tab-container">
          <div class="tab-item">
            <div class="icon tab-icon1"></div>
            <p>可信接入认证</p>
          </div>
          <div class="tab-item">
            <div class="icon tab-icon2"></div>
            <p>终端安全管控</p>
          </div>
          <div class="tab-item">
            <div class="icon tab-icon3"></div>
            <p>互联网直连</p>
          </div>
          <div class="tab-item">
            <div class="icon tab-icon4"></div>
            <p>登记专机专用</p>
          </div>
          <div class="tab-item">
            <div class="icon tab-icon5"></div>
            <p>离线本地缓存</p>
          </div>
          <div class="tab-item">
            <div class="icon tab-icon6"></div>
            <p>身份证阅读器支持</p>
          </div>
          <div class="tab-item">
            <div class="icon tab-icon7"></div>
            <p>扫描仪证件通支持</p>
          </div>
        </div>
        <div class="tomore">了解更多>></div>
      </div>
    </section>
    <section class="content-container content-container2" ref="sedItem">
      <div class="text-container text-container2" :class="{'run-text-2': runFlag2}">
        <h3>安全终端开放服务接入方案</h3>
        <p class="content">安旅科技以开放化、服务化、智能化为目标，通过开放平台、易公安安全终端建立了开放服务接入方案，实现了人证核验设备接入、自助机登记服务、PMS数据互通服务，为未来酒店智能化、无人化提供了基础。,从而提升了旅客入住体验、简化了前台登记流程、提高了采集数据质量。</p>
        <div class="tab-container2">
          <div class="tab-item">
            <div class="icon tab-icon8"></div>
            <p>开放平台</p>
          </div>
          <div class="tab-item">
            <div class="icon tab-icon9"></div>
            <p>人证核验设备接入</p>
          </div>
          <div class="tab-item">
            <div class="icon tab-icon10"></div>
            <p>自助机登记服务</p>
          </div>
          <div class="tab-item">
            <div class="icon tab-icon11"></div>
            <p>PMS数据互通服务</p>
          </div>
        </div>
        <div class="tomore" @click="gogogo">了解更多>></div>
      </div>
      <div class="img2"></div>
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
      imgList: [
        {
          url:'../../assets/herderpic1.png'
        },
        {
          url:'../../assets/herderpic2.png'
        },
        {
          url:'../../assets/herderpic3.png'
        },
        {
          url:'../../assets/herderpic4.png'
        },
      ],
      topHeight: '0px',
      screenWidth: document.body.clientWidth,
      runFlag: false,
      runFlag2: false
    }
  },
  created() {
    this.topHeight = document.body.clientWidth/3.6 -10 + 'px'
    setTimeout(()=> {
      this.runFlag = true
    },200)
  },
  mounted() {
    window.onresize = () => {
        return (() => {
            window.screenWidth = document.body.clientWidth
            this.screenWidth = window.screenWidth
        })()
    }
    // console.log(this.$refs.sedItem.scrollTop)
    window.addEventListener('scroll', (e)=> {
      let scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop
      let itemTop = this.$refs.sedItem.offsetTop
      let windowHeight = window.innerHeight
      if (scrollTop-200 + windowHeight > itemTop) {
        this.runFlag2 = true
      }
    })
    
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
      location.assign('../product.html')
    },
    tototo() {
      location.assign('../user/login.html')
    }
  }
}
</script>

<style lang="postcss">
.top-img{
  width:100%;
  /* height: 556px; */
}
.content-container{
  display: flex;
  flex-direction: row;
  justify-content:space-between;
}
.content-container2{
  justify-content: space-between;
}
.content-container .img1{
  width: 800px;
  height: 720px;
  /* overflow: hidden;
  position: relative; */
  background:transparent url('../../assets/sy_t1.png') no-repeat;
}
.content-container .img2{
  width: 800px;
  height: 720px;
  background:transparent url('../../assets/sy_t2.png') no-repeat;
  background-position:-200px 0px;
}
.content-container .text-container{
  width: 649px;
  margin: 90px 100px 0 100px;
}
@media screen and (min-width: 1850px){
  .run-text-1{
    transform: translate(-40%,0px);
    transition: transform 1s;
  }
  .run-text-2{
    transform: translate(30%,0px);
    transition: transform 1s;
  }
}
@media screen and (max-width: 1850px){
  .run-text-1{
    transform: translate(-15%,0px);
    transition: transform 1s;
  }
  .run-text-2{
    transform: translate(15%,0px);
    transition: transform 1s;
  }
}

.content-container .text-container2{
  /* margin-left:373px; */
  /* justify-content:f; */
  width: 749px;
}
.content-container h3 {
  font-size: 29px;
  font-size:29px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(51,51,51,1);
  line-height: 29px;
}

.content-container .content {
  margin-top: 44px;
  font-size:15px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(102,102,102,1);
  line-height:29px;
}
.tab-container {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  flex-wrap: wrap;
}
.tab-container2 {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  flex-wrap: wrap;
  margin-top: 30px;
}
.tomore {
  font-size:15px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(102,102,102,1);
  line-height:29px;
  cursor: pointer;
  float: right;
  margin-top: 30px;
}
.tab-item {
  width: 25%;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  height: 90px;
  margin-top: 40px;
}
.tab-item p {
  font-size:12px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(102,102,102,1);
  line-height:29px;
  white-space:nowrap;
  width: 100%;
  text-overflow: ellipsis;
  overflow: hidden;
  text-align: center;
}
.icon {
  background:transparent url('../../assets/sy_icon.png') no-repeat;
}
.tab-icon1 {
  width: 32px;
  height: 39px;
  background-position:-86px -86px;
}
.tab-icon2 {
  width: 36px;
  height: 39px;
  background-position:-279px -90px;
}
.tab-icon3 {
  width: 40px;
  height: 39px;
  background-position:-473px -87px;
}
.tab-icon4 {
  width: 40px;
  height: 39px;
  background-position:-658px -89px;
}
.tab-icon5 {
  width: 40px;
  height: 39px;
  background-position:-81px -239px;
}
.tab-icon6 {
  width: 47px;
  height: 39px;
  background-position:-274px -236px;
}
.tab-icon7 {
  width: 40px;
  height: 39px;
  background-position:-471px -235px;
}
.tab-icon8 {
  width: 40px;
  height: 39px;
  background-position:-85px -444px;
}
.tab-icon9 {
  width: 50px;
  height: 39px;
  background-position:-261px -447px;
}
.tab-icon10 {
  width: 47px;
  height: 39px;
  background-position:-464px -443px;
}
.tab-icon11 {
  width: 42px;
  height: 41px;
  background-position:-665px -442px;
}

</style>
