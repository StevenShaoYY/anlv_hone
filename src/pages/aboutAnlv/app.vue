<template>
  <div id="app">
    <top-bar :active="'7'"></top-bar>
     <div >
        <img class="top-img" src="../../assets/aboutAnlv.png" alt="">
    </div>
    <section class="main">
      <div class="main-c">
        <h3 class="title">安旅简介</h3>
        <div class="content2">
          <p>&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp杭州安旅科技有限公司成立于2016年，坐落于杭州滨江高新技术产业区，是一家专门从事软件产品开发和系统集成的信息技术公司，为全国旅馆业住宿管理提供应用产品和技术解决方案，包括互联网+酒店入住登记系统、人脸识别技术、身份证门锁技术等。安旅科技致力于为政府部门提供创新的社会治理解决方案，提高住宿行业的生产效率。</p>
          <p>&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp公司已与华住集团、阿里未来酒店等大型酒店业集团签订战略合作协议，为其旗下上千家连锁酒店提供产品和项目解决方案；同时根据地方政府需求，在杭州、温州、嘉兴等地酒店进行产品部署工作</p>
        </div>
         <h3 class="title">团队介绍</h3>
        <div class="content2">
          <p>&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp杭州安旅科技有限公司拥有众多优秀的高科技人才，创始研发团队均来自行业核心技术专家，曾参与浙江省110接处警系统、新一代移动警务平台等多个大型项目的研发工作，具有丰富的技术研发和行业业务经验。</p>
        </div>
      </div>
      <div class="add-box">
        <div @click="goTo('concatus.html')" class="box-item">
          <div class="icon-1"></div>
          <p>联系我们</p>
        </div>
        <div @click="goTo('addAnlv.html')" class="box-item">
          <div class="icon-2"></div>
          <p>加入安旅</p>
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
    bottom,
  },
  data() {
    return {
     
    }
  },
  created() {
  },
  mounted() {
    
  },
  methods: {
    goTo(url) {
      location.assign(`../${url}`)
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
  width: 1200px;
  
}
.bottom-last {
  margin-bottom: 80px;
}
.img-container img + img{
  margin-left: 10px;
}
.last-img {
  margin-left: 0px !important;
  margin-top: 10px;
  margin-bottom: 100px;
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
  flex-direction: column;
  justify-content: center;
  margin-top: 30px;
  font-size: 16px;
  margin-bottom: 100px;
}

.add-box{
  height: 262px;
  width: 100%;
  background:#F2F3f4;
  display: flex;
  justify-content: center;
  align-items: center;
}
.add-box .box-item{
  width: 351px;
  height: 210px;
  background:rgba(255,255,255,1);
  border:1px solid rgba(204, 204, 204, 1);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
.add-box .box-item + .box-item {
  margin-left: 100px;
}
.box-item p {
  font-size:24px;
font-family:MicrosoftYaHei;
font-weight:400;
color:rgba(0,0,0,1);
line-height:30px;
}
.icon-1{
  width: 82px;
  height: 82px;
  background:transparent url('../../assets/proicon.png') no-repeat;
  background-position:-738px -47px;
}
.icon-2{
  width: 56px;
  height: 72px;
  background:transparent url('../../assets/addAlv.png') no-repeat;
}
</style>
