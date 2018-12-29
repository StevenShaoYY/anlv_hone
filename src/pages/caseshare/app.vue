<template>
  <div id="app">
    <top-bar :active="'5'"></top-bar>
    <div :height="topHeight">
        <img class="top-img" src="../../assets/caseshare.png" alt="">
    </div>
    <section class="main">
      <div class="ct-item content-item1" id="miao1">
        <div class="text-item">
          <h3>石基昆仑PMS对接</h3>
          <p>
            安旅科技与石基昆仑PMS对接，实现未来酒店无人化方案。旅客入住登记取卡可在1分钟内完成,极大的提升了旅客入住体验。
          </p>
        </div>
      </div>
      <div class="ct-item content-item2" id="miao2">
        <div class="text-item">
          <h3>华住易掌柜自助机对接</h3>
          <p>
            安旅科技与华住易掌柜自助机对接，在全季酒店上线使用，省去了前台身份证登记操作，提高了工作效率。
          </p>
        </div>
      </div>
      <div class="ct-item content-item3" id="miao3">
        <div class="text-item">
          <h3>魔点人证核验设备对接</h3>
          <p>
            安旅科技与魔点科技的人证核验设备对接，实现了旅客入住人证核验功能。
          </p>
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
@media screen and (max-width: 1200px){
.main {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.main-c{
  padding: 0 40px
}
.ct-item{
  width: 100%;
  height: 500px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.content-item1 .text-item{
  margin-left: 50%;
}
.content-item2 .text-item{
  margin-right: 50%;
}
.content-item3 .text-item{
  margin-left: 50%;
}

.ct-item h3{
  padding: 0 20px;
  font-size:30px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(51,51,51,1);
}
.ct-item p{
  margin-top: 25px;
  /* width: 515px; */
  padding: 0 20px;
  font-size:16px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(102,102,102,1);
}
.content-item1{
  width: 100%;
  background:transparent url('../../assets/sharecase-pic1.png') no-repeat;
  background-size:100% 100%;
}
.content-item2{
  width: 100%;
  background:transparent url('../../assets/sharecase-pic2.png') no-repeat;
  background-size:100% 100%;
}
.content-item3{
  width: 100%;
  background:transparent url('../../assets/sharecase-pic3.png') no-repeat;
  background-size:100% 100%;
}
.bottom-last {
  margin-bottom: 80px;
}
.top-img{
  width:100%;
}
}

@media screen and (min-width: 1200px){
.main {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.main-c{
  width: 960px;
}
.ct-item{
  width: 100%;
  height: 500px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.content-item1 .text-item{
  margin-left: 500px;
}
.content-item2 .text-item{
  margin-right: 500px;
}
.content-item3 .text-item{
  margin-left: 500px;
}

.ct-item h3{
  font-size:30px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(51,51,51,1);
}
.ct-item p{
  margin-top: 25px;
  width: 515px;
  font-size:16px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(102,102,102,1);
}
.content-item1{
  width: 100%;
  background:transparent url('../../assets/sharecase-pic1.png') no-repeat;
  background-size:100% 100%;
}
.content-item2{
  width: 100%;
  background:transparent url('../../assets/sharecase-pic2.png') no-repeat;
  background-size:100% 100%;
}
.content-item3{
  width: 100%;
  background:transparent url('../../assets/sharecase-pic3.png') no-repeat;
  background-size:100% 100%;
}
.bottom-last {
  margin-bottom: 80px;
}
.top-img{
  width:100%;
}
}
</style>
