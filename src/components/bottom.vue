<template lang="html">
  <footer>
    <div class="w960">
      <div class="first-container">
        <div class="url-container">
          <ul class="url-list">
            <li class="url-title">关于安旅</li>
            <li class="url-content">安旅简介</li>
            <li class="url-content">加入安旅</li>
          </ul>
          <ul class="url-list">
            <li class="url-title">服务支持</li>
            <li class="url-content">下载中心</li>
            <li class="url-content">联系我们</li>
          </ul> 
          <ul class="url-list">
            <li class="url-title">旅业登记</li>
            <li class="url-content">开通说明</li>
            <li class="url-content">使用手册</li>
          </ul> 
          <ul class="url-list">
            <li class="url-title">开放平台</li>
            <li class="url-content">接入说明</li>
            <li class="url-content">开发手册</li>
          </ul> 
          <ul class="url-list">
            <li class="url-title">案例分享</li>
            <li class="url-content">PMS对接</li>
            <li class="url-content">自助机对接</li>
            <li class="url-content">人证核验设备对接</li>
          </ul>
        </div>
        <div class="code-container">
          <div class="code-item">
            <!-- <img class="code-img" src="../assets/herderpic.png" alt=""> -->
            <p>安旅小程序</p>
          </div>
          <div class="code-item">
            <!-- <img class="code-img" src="../assets/herderpic.png" alt=""> -->
            <p>安旅公众号</p>
          </div>
        </div>
      </div>
      <div class="sed-container">
        <p>浙ICP备xxxxx号© 2018 All rights reserved.Powered by AnlvTechnology.</p>
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
    display: flex;
    justify-content: center;
    background-color: #2A364A;
    height: 288px;
    color: #97a3b7;
  }
  footer .w960 {
    height: 288px;
    width: 960px;
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
    margin-left: 50px;
  }
  footer .sed-container {
    color: #97a3b7;
    margin-top: 30px;
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
  }
  .url-container .url-list{
    width: 160px;
  }
  .url-container .url-list .url-content{
    font-size: 14px;
    line-height: 40px;
  }
  .url-container .url-title {
    font-size: 20px;
    line-height: 50px;
    font-weight: 500;
  }
</style>
