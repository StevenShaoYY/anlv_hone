<template>
  <div id="app">
    <top-bar :active="'4-1'"></top-bar>
    <div :height="topHeight">
        <img class="top-img" src="../../assets/userbook.png" alt="">
    </div>
    <section class="main">
      <div class="main-c">
        <h3 class="title">使用手册</h3>
        <div class="content">
          <a class="box-item" href="./doc/易公安用户手册.pdf" download>
            <h4>易公安使用手册</h4>
            <p>介绍易公安的使用说明，主要包括易公安安装、用户管理、旅客登记、旅客离店等功能。</p>
          </a>
          <a class="box-item">
            <h4>安旅快录使用手册</h4>
            <p>介绍安旅快录的使用说明，主要包括安旅快录的安装、旅客登记一次性录入等功能。</p>
          </a>
          <a class="box-item" href="./doc/安旅助手用户手册.pdf" download>
            <h4>安旅助手使用手册</h4>
            <p>介绍安旅助手的使用说明，主要包括无证登记、人证核验、草稿箱管理等功能。</p>
          </a>
        </div>
      </div>
      <div class="main-c bottom-last">
        <h3 class="title">常见问题解答</h3>
        <div class="content">
          <div class="box-item no-pointer">
            <h4>问：登录时提示当前时间不正确</h4>
            <p>答：原因是网络未连接，请检查网络连接是否正常，如有疑问请咨询宽带运营商。</p>
          </div>
          <div class="box-item no-pointer">
            <h4>问：有线网络未连接</h4>
            <p>答：页面显示网络未连接，点击右下角网络图标，进入网络设置，查看和配置网络链接。</p>
          </div>
          <div class="box-item no-pointer">
            <h4>问：身份证读不出信息怎么登记</h4>
            <p>答：使用安旅助手扫描证件登记或无证登记。</p>
          </div>
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
@media screen and (min-width: 1200px){

.main-c{
  width: 1200px;
}
.content .box-item{
  width: 390px;
  height: 161px;
  border:1px solid rgba(204, 204, 204, 1);
  cursor: pointer;
}
.no-pointer{
  cursor: default !important;
}
}
@media screen and (max-width: 1200px){

.main-c{
  padding: 0 20px;
}
.main{
min-height: calc(100vh - 547px);
}
.content .box-item{
  width: 30%;
  height: 200px;
  border:1px solid rgba(204, 204, 204, 1);
  cursor: pointer;
}
.no-pointer{
  cursor: default !important;
}
}
.main {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
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
