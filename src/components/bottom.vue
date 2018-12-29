<template lang="html">
  <footer>
    <div class="w960">
      <div class="first-container">
        <div class="url-container">
          <ul class="url-list">
            <li class="url-title">关于安旅</li>
            <li class="url-content" @click="goTo('aboutAnlv.html')">安旅简介</li>
            <li class="url-content" @click="goTo('addAnlv.html')">加入安旅</li>
          </ul>
          <ul class="url-list">
            <li class="url-title">服务支持</li>
            <li class="url-content" @click="goTo('downloadcenter.html')">下载中心</li>
            <li class="url-content" @click="goTo('contact.html')">联系我们</li>
          </ul> 
          <ul class="url-list">
            <li class="url-title">旅业登记</li>
            <li class="url-content" @click="goTo('fixplan1.html')">解决方案</li>
            <li class="url-content" @click="goTo('usebook.html')">使用手册</li>
          </ul> 
          <ul class="url-list">
            <li class="url-title">开放平台</li>
            <li class="url-content" @click="goTo('openplan.html')">接入说明</li>
            <li class="url-content" @click="goTo('openplan.html#miao2')">开发手册</li>
          </ul> 
          <ul class="url-list">
            <li class="url-title">案例分享</li>
            <li class="url-content" @click="goTo('caseshare.html')">PMS对接</li>
            <li class="url-content" @click="goTo('caseshare.html#miao2')">自助机对接</li>
            <li class="url-content" @click="goTo('caseshare.html#miao3')">人证核验设备对接</li>
          </ul>
        </div>
        <div class="code-container">
          <div class="code-item">
            <img class="code-img" src="../assets/u67.jpg" alt="">
            <p style="margin-top:20px;">安旅小程序</p>
          </div>
          <div class="code-item">
            <img class="code-img" src="../assets/u77.jpg" alt="">
            <p style="margin-top:20px;">安旅公众号</p>
          </div>
        </div>
      </div>
      <div class="sed-container">
        <p>Copyright© 2018 Powered by AnlvTechnology | 浙ICP备17005608号-1</p>
      </div>
    </div>
  </footer>
</template>

<script>
import 'normalize.css'
export default {
  props:{
    active: {
      type: String,
      default: '1'
    },
  },
  data() {
    return {
    }
  },
  methods: {
    goTo(url) {
      location.assign(`../${url}`)
    }
  }
}
</script>

<style lang="css">
  footer {
    width: 100%;
    height: 300px;
    display: flex;
    justify-content: center;
    /* background-color: #2A364A; */
    background:transparent url('../assets/bottom.png') no-repeat;
    background-size:100% 100%;
    height: 288px;
    color: #97a3b7;
  }
  footer .w960 {
    height: 288px;
    flex:0 1 960px;
    display: flex;
    flex-direction: column;
  }
  footer .first-container {
    display: flex;
    flex-direction: row;
    margin-top: 40px;
  }
  footer .code-container {
    display: flex;
    flex-direction: row;
    margin-left: 5%;
  }
  footer .sed-container {
    color: #ffffff;
    margin-bottom: 30px;
  }
  .code-item {
    color: #97a3b7;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-size: 16px;
    margin-left: 20px;
    width: 115px;
  }
  footer .url-container {
    display: flex;
    flex-direction: row;
    color: #97a3b7;
    flex: 1;
  }
  .url-container .url-list{
    flex:0 1 160px;
  }
  .url-container .url-list .url-content{
    font-size: 14px;
    line-height: 40px;
    cursor: pointer;
    color: #999999;
  }
  .url-container .url-title {
    font-size: 20px;
    line-height: 50px;
    font-weight: 500;
    color: #ffffff;
  }
</style>
