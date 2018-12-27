<template>
  <div id="app">
    <top-bar :active="'4-3'"></top-bar>
    <div :height="topHeight">
        <img class="top-img" src="../../assets/downloadcenter.png" alt="">
    </div>
    <section class="main">
      <div class="main-c">
        <h3 class="title">下载中心</h3>
        <div class="content2">
            <div class="title-container"><div class="icon-book"></div>安旅助手用户手册</div>
            <a href="./doc/安旅助手用户手册.pdf" download  class="btn-container"><div class="icon-down"></div>下载</a>
        </div>
        <div class="content2">
            <div class="title-container"><div class="icon-book"></div>易公安用户手册</div>
            <a href="./doc/易公安用户手册.pdf" download   class="btn-container"><div class="icon-down"></div>下载</a>
        </div>
        <div class="content2">
            <div class="title-container"><div class="icon-book"></div>常见问题</div>
            <a href="./doc/常见问题.pdf" download   class="btn-container"><div class="icon-down"></div>下载</a>
        </div>
        <div class="content2">
            <div class="title-container"><div class="icon-book"></div>护照登记使用流程</div>
            <a href="./doc/护照登记.pdf" download   class="btn-container"><div class="icon-down"></div>下载</a>
        </div>
        <div class="content2">
            <div class="title-container"><div class="icon-book"></div>驾驶证扫码登记使用流程</div>
            <a href="./doc/驾驶证扫码登记.pdf" download  class="btn-container"><div class="icon-down"></div>下载</a>
        </div>
        <div class="content2">
            <div class="title-container"><div class="icon-book"></div>身份证机读登记使用流程</div>
            <a href="./doc/身份证机读登记.pdf" download   class="btn-container"><div class="icon-down"></div>下载</a>
        </div>
        <div class="content2">
            <div class="title-container"><div class="icon-book"></div>身份证扫码登记使用流程</div>
            <a href="./doc/身份证扫码登记.pdf" download   class="btn-container"><div class="icon-down"></div>下载</a>
        </div>
        <div class="content2 bottom-last">
            <div class="title-container"><div class="icon-book"></div>无证登记使用流程</div>
            <a href="./doc/无证登记.pdf" download   class="btn-container"><div class="icon-down"></div>下载</a>
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
    download(doc) {
      window.location.href = `https://www.baidu.com/assets/doc/${doc}`
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
.main-c{
  width: 960px;
  
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
.content2 {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 125px;
  border-bottom: 3px dotted rgba(211,211,211,1);
}
.title-container{
  display: flex;
  font-size:20px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(51,51,51,1);
}
.btn-container{
  display: flex;
  line-height: 36px;
  color: #067Dff;
  border-radius: 18px;
  padding: 0 15px;
  border: 1px solid #067Dff;
  cursor: pointer;
}
.icon-book{
  width: 40px;
  height: 38px;
  background:transparent url('../../assets/proicon.png') no-repeat;
  background-position:-568px -71px;
}
.icon-down{
  width: 40px;
  height: 36px;
  background:transparent url('../../assets/proicon.png') no-repeat;
  background-position:-647px -70px;
}
</style>
