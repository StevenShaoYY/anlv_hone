<template>
  <div id="app">
    <top-bar :active="'2'"></top-bar>
    <div>
        <img class="top-img" src="../../assets/proheader.png" alt="">
    </div>
    <div class="h2-container">
      <h2>硬件产品</h2>
    </div>
    <section class="content-container" @click="goTo('productplan1.html')">
      <div class="title-container">
        <div class="yigongan-small"></div>
        <p>易公安</p>
      </div>
      <div class="text-container">
        <div class="yigongan-pic" :class="{'run-text-1': runFlag}"></div>
        <div class="right-container" :class="{'run-text-2': runFlag}">
          <div class="right-header">
            <h3>互联网升级，开放服务接入</h3>
          </div>
          <div class="tab-container">
            <div class="tab-item">
              <div class="icon tab-icon1"></div>
              <p>互联网直连</p>
            </div>
            <div class="tab-item">
              <div class="icon tab-icon2"></div>
              <p>专用安全终端</p>
            </div>
            <div class="tab-item">
              <div class="icon tab-icon3"></div>
              <p>支持人证核验</p>
            </div>
            <div class="tab-item">
              <div class="icon tab-icon4"></div>
              <p>开放服务接入</p>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="content-container" @click="goTo('productplan2.html')" ref="sedItem">
      <div class="title-container fr">
        <div class="suzhu-small"></div>
        <p>安旅速住</p>
      </div>
      <div class="text-container">
        <div class="right-container right-sed" :class="{'run-text-3': runFlag2}">
          <div class="right-header">
            <h3>功能集成，简单易用</h3>
          </div>
          <div class="tab-container">
            <div class="tab-item">
              <div class="icon tab-icon11"></div>
              <p>易公安功能集成</p>
            </div>
            <div class="tab-item">
              <div class="icon tab-icon22"></div>
              <p>内置身份证阅读器</p>
            </div>
            <div class="tab-item">
              <div class="icon tab-icon33"></div>
              <p>内置登记客户端</p>
            </div>
            <div class="tab-item">
              <div class="icon tab-icon44"></div>
              <p>支持安旅快录</p>
            </div>
          </div>
        </div>
        <div class="suzhu-pic" :class="{'run-text-4': runFlag2}"></div>
      </div>
    </section>
    <section class="content-container" @click="goTo('productplan3.html')" ref="thdItem">
      <div class="title-container">
        <div class="kuailu-small"></div>
        <p>安旅快录</p>
      </div>
      <div class="text-container">
        <div class="kuailu-pic" :class="{'run-text-1': runFlag3}"></div>
        <div class="right-container" :class="{'run-text-2': runFlag3}">
          <div class="right-header">
            <h3>外设扩展，数据互通</h3>
          </div>
          <div class="tab-container">
            <div class="tab-item">
              <div class="icon tab-icon111"></div>
              <p>支持护照阅读仪</p>
            </div>
            <div class="tab-item">
              <div class="icon tab-icon222"></div>
              <p>支持身份证读取</p>
            </div>
            <div class="tab-item">
              <div class="icon tab-icon333"></div>
              <p>PMS数据复用</p>
            </div>
            <div class="tab-item">
              <div class="icon tab-icon444"></div>
              <p>PC端管理集成</p>
            </div>
          </div>
        </div>
      </div>
    </section>
    <div class="h2-container h2-container2">
      <h2>软件产品</h2>
    </div>
    <div class="software-container" ref="fourItem">
        <img class="software-img" :class="{'run': runFlag4}" src="../../assets/software1.png" alt="">
        <img class="software-img" :class="{'run': runFlag4}" src="../../assets/software2.png" alt="">
        <img class="software-img" :class="{'run': runFlag4}" src="../../assets/software3.png" alt="">
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
      screenWidth: document.body.clientWidth,
      runFlag:false,
      runFlag2:false,
      runFlag3:false,
      runFlag4:false
    }
  },
  created() {
    this.topHeight = document.body.clientWidth/3.6 -10 + 'px';
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
    window.addEventListener('scroll', (e)=> {
      let scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop
      let itemTop = this.$refs.sedItem.offsetTop
      let itemTop2 =this.$refs.thdItem.offsetTop
      let itemTop3 = this.$refs.fourItem.offsetTop
      let windowHeight = window.innerHeight

      if (scrollTop-150 + windowHeight > itemTop) {
        this.runFlag2 = true
      }
      if (scrollTop-150 + windowHeight > itemTop2) {
        this.runFlag3 = true
      }
      if (scrollTop-100 + windowHeight > itemTop3) {
        this.runFlag4 = true
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
    goTo(url) {
      location.assign(`../${url}`)
    }
  }
}
</script>

<style lang="postcss">
@media screen and (min-width: 1200px){
  .top-img{
    width:100%;
  }
  .h2-container{
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
  }
  .h2-container2{
    margin-top: 150px;
  }
  .h2-container h2{
    height: 130px;
    width: 1200px;
    line-height: 130px;
    font-size:36px;
    font-family:MicrosoftYaHei;
    font-weight:400;
    color:rgba(0,0,0,1);
  }
  .content-container{
    width: 100%;
    min-height:350px;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    margin-top: 100px;
    cursor: pointer;
  }
  .content-container + .content-container {
    margin-top: 200px;
  }
  .title-container {
    width: 1200px;
    display: flex;
    flex-direction: row;
    align-items: center;
    margin-left: 50px;
  }
  .fr {
    justify-content: flex-end;
    padding-right: 100px;
  }
  .title-container p{
    padding-left: 12px;
    font-size:30px;
    font-family:MicrosoftYaHei;
    font-weight:400;
    color:rgba(1,1,1,1); 
  }
  .yigongan-pic{
    width: 300px;
    height: 300px;
    
    position: absolute;
    left: -300px;
    
    background:transparent url('../../assets/proicon.png') no-repeat;
    background-position:-100px -166px;
  }
  .yigongan-small{
    width: 50px;
    height: 43px;
    background:transparent url('../../assets/proicon.png') no-repeat;
    background-position:-246px -68px;
  }
  .suzhu-small{
    width: 72px;
    height: 36px;
    background:transparent url('../../assets/proicon.png') no-repeat;
    background-position:-330px -70px;
  }
  .suzhu-pic{
    width: 350px;
    height: 300px;
    position: absolute;
    right: -400px;

    background:transparent url('../../assets/proicon.png') no-repeat;
    background-position:-490px -184px;
  }
  .kuailu-small{
    width: 58px;
    height: 54px;
    background:transparent url('../../assets/proicon.png') no-repeat;
    background-position:-422px -61px;
  }
  .kuailu-pic{
    width: 300px;
    height: 300px;
    position: absolute;
    left: -300px;
    
    background:transparent url('../../assets/proicon.png') no-repeat;
    background-position:-921px -176px;
  }
  .text-container {
    display: flex;
    /* position: relative; */
  }
  .right-container {
    position: absolute;
    right: -1000px;
    
    width: 800px;
    display: flex;
    height: 70px;
    margin-left: 100px;
    /* margin-right: -1200px; */
    flex-direction: column;
    justify-content: flex-start;
  }
  .run-text-1{
    animation-name: oDiv;
    animation-duration: 1s;
    animation-fill-mode: forwards;
    animation-timing-function:ease-in;
  }
  @keyframes oDiv{
    0%{left:-300px;opacity: 0;}
    80%{left:20%;}
    100%{position:static;opacity: 1;}
  }
  .run-text-2{
    animation-name: oDiv2;
    animation-duration: 1s;
    animation-fill-mode: forwards;
    animation-timing-function:ease-in;
  }
  @keyframes oDiv2{
    0%{right:-200px;opacity: 0;}
    80%{right:20%;}
    100%{position:static;opacity: 1;}
  }

  .run-text-3{
    animation-name: oDiv3;
    animation-duration: 1s;
    animation-fill-mode: forwards;
    animation-timing-function:ease-in;
  }
  @keyframes oDiv3{
    0%{left:-300px;opacity: 0;}
    80%{left:20%;}
    100%{position:static;opacity: 1;}
  }
  .run-text-4{
    animation-name: oDiv4;
    animation-duration: 1s;
    animation-fill-mode: forwards;
    animation-timing-function:ease-in;
  }
  @keyframes oDiv4{
    0%{right:-200px;opacity: 0;}
    80%{right:20%;}
    100%{position:static;opacity: 1;}
  }


  .right-sed{ 
    width: 750px;
    margin-left: 0px;
    margin-right: 100px;
  }
  .right-header {
    border-bottom: 3px solid rgba(233,233,233,1);
  }
  .right-header h3{
    font-size:24px;
    line-height: 70px;
    font-family:MicrosoftYaHei;
    font-weight:400;
    color:rgba(102,102,102,1);
  }



  .tab-container {
    margin-top: 40px;
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
  .tab-item {
    width: 25%;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    height: 130px;
    margin-top: 40px;
  }
  .tab-item p {
    font-size:20px;
    font-family:MicrosoftYaHei;
    font-weight:400;
    color:rgba(102,102,102,1);
    line-height:50px;
    white-space:nowrap;
    width: 100%;
    text-overflow: ellipsis;
    overflow: hidden;
    text-align: center;
  }
  .software-img{
    width: 395px;
    height: 261px;
    margin-left: 20px;
    margin-top: 30px;
    opacity: 0;
  }
  .run{
    animation-name: oDiv5;
    animation-duration: 1.5s;
    animation-fill-mode: forwards;
    animation-timing-function:ease-in;
  }
  @keyframes oDiv5{
    0%{opacity: 0;}
    100%{opacity: 1;}
  }

  .software-container {
    display: flex;
    justify-content: center;
    height: 400px;
  }
}

@media screen and (max-width: 1200px){
  .top-img{
    width:100%;
  }
  .h2-container{
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
  }
  .h2-container2{
    margin-top: 150px;
  }
  .h2-container h2{
    height: 130px;
    /* width: 1200px; */
    line-height: 130px;
    font-size:36px;
    font-family:MicrosoftYaHei;
    font-weight:400;
    color:rgba(0,0,0,1);
  }
  .content-container{
    width: 100%;
    min-height:350px;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    margin-top: 100px;
    cursor: pointer;
  }
  .content-container + .content-container {
    margin-top: 200px;
  }
  .title-container {
    width: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    padding-left: 50px;
  }
  .fr {
    justify-content: flex-end;
    padding-right: 100px;
  }
  .title-container p{
    padding-left: 12px;
    font-size:30px;
    font-family:MicrosoftYaHei;
    font-weight:400;
    color:rgba(1,1,1,1); 
  }
  .yigongan-pic{
    width: 300px;
    height: 300px;
    background:transparent url('../../assets/proicon.png') no-repeat;
    background-position:-100px -166px;
  }
  .yigongan-small{
    width: 50px;
    height: 43px;
    background:transparent url('../../assets/proicon.png') no-repeat;
    background-position:-246px -68px;
  }
  .suzhu-small{
    width: 72px;
    height: 36px;
    background:transparent url('../../assets/proicon.png') no-repeat;
    background-position:-330px -70px;
  }
  .suzhu-pic{
    width: 350px;
    height: 300px;

    background:transparent url('../../assets/proicon.png') no-repeat;
    background-position:-490px -184px;
  }
  .kuailu-small{
    width: 58px;
    height: 54px;
    background:transparent url('../../assets/proicon.png') no-repeat;
    background-position:-422px -61px;
  }
  .kuailu-pic{
    width: 300px;
    height: 300px;
    background:transparent url('../../assets/proicon.png') no-repeat;
    background-position:-921px -176px;
  }
  .text-container {
    display: flex;
    /* position: relative; */
  }
  .right-container {
    width: calc(100% - 350px);
    display: flex;
    height: 70px;
    margin-left: 100px;
    /* margin-right: -1200px; */
    flex-direction: column;
    justify-content: flex-start;
  }
.right-sed{ 
    /* width: 750px; */
    width: calc(100% - 350px);
    margin-left: 0px;
    /* margin-right: 100px; */
  }
  .right-header {
    border-bottom: 3px solid rgba(233,233,233,1);
  }
  .right-header h3{
    font-size:24px;
    line-height: 70px;
    font-family:MicrosoftYaHei;
    font-weight:400;
    color:rgba(102,102,102,1);
  }


  .tab-container {
    margin-top: 40px;
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
  .tab-item {
    width: 25%;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    height: 130px;
    margin-top: 40px;
  }
  .tab-item p {
    font-size:20px;
    font-family:MicrosoftYaHei;
    font-weight:400;
    color:rgba(102,102,102,1);
    line-height:50px;
    white-space:nowrap;
    width: 100%;
    text-overflow: ellipsis;
    overflow: hidden;
    text-align: center;
  }
  .software-img{
    width: 30%;
    height: 261px;
    margin-left: 20px;
    margin-top: 30px;
    opacity: 0;
  }
  .run{
    animation-name: oDiv5;
    animation-duration: 1.5s;
    animation-fill-mode: forwards;
    animation-timing-function:ease-in;
  }
  @keyframes oDiv5{
    0%{opacity: 0;}
    100%{opacity: 1;}
  }

  .software-container {
    display: flex;
    justify-content: center;
    height: 400px;
  }
}

.icon {
  background:transparent url('../../assets/proicon.png') no-repeat;
}
.tab-icon1 {
  width: 90px;
  height: 85px;
  background-position:-1240px -112px;
}
.tab-icon2 {
  width: 90px;
  height: 85px;
  background-position:-1447px -112px;
}
.tab-icon3 {
  width: 90px;
  height: 85px;
  background-position:-1667px -112px;
}
.tab-icon4 {
  width: 90px;
  height: 85px;
  background-position:-1867px -112px;
}

.tab-icon11 {
  width: 90px;
  height: 85px;
  background-position:-1240px -251px;
}
.tab-icon22 {
  width: 90px;
  height: 85px;
  background-position:-1469px -251px;
}
.tab-icon33 {
  width: 90px;
  height: 85px;
  background-position:-1677px -251px;
}
.tab-icon44 {
  width: 90px;
  height: 85px;
  background-position:-1868px -251px;
}
.tab-icon111 {
  width: 90px;
  height: 85px;
  background-position:-1241px -401px;
}
.tab-icon222 {
  width: 90px;
  height: 85px;
  background-position:-1441px -401px;
}
.tab-icon333 {
  width: 90px;
  height: 85px;
  background-position:-1650px -401px;
}
.tab-icon444 {
  width: 90px;
  height: 85px;
  background-position:-1871px -401px;
}
</style>
