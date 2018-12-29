<template>
  <div id="app">
    <top-bar :active="'7'"></top-bar>
     <div >
        <img class="top-img" src="../../assets/addAnlv.png" alt="">
    </div>
    <section class="main">
      <div class="main-c">
        <h3 class="title">web前端开发</h3>
        <div class="content2">
          <p>学历：本科及本科以上</p>
          <p>地点：杭州</p>
          <p>经验：2年以上</p>
        </div>
        <div class="content3">
          <h3 class="title2">岗位概述</h3>
          <p>根据页面原型开发前端代码，配合后端开发人员完成数据的对接和页面调试工作以及配合产品经理对系统和产品进行初步的交互设计工作。</p>
          <h3 class="title2">职责</h3>
          <p>1、根据页面原型开发前端代码，配合后端开发人员完成数据的对接和页面调试工作；</p>
          <p>2、根据页面原型进行前端页面代码的开发;</p>
          <p>3、配合后端开发人员完成页面整合和调试工作；</p>
          <p>4、解决不同的浏览器及不同版本的兼容性问题；</p>
          <p>5、参与 JS类库等前端库开发和新技术研究工作。</p>
          <p>6、配合产品经理，根据产品和系统需求制作产品交互原型。</p>
          <h3 class="title2">要求</h3>
          <p>1、1年及以上相关工作经验，有大型互联网公司工作经验优先考虑；</p>
          <p>2、精通web前端开发技术，熟悉(X)HTML/CSS/Javascript/ HTML5；熟练掌握跨浏览器和终端开发，熟悉前端性能优化，并有相关经验</p>
          <p>3、对新的前端开发技术有强烈热情，个性乐观开朗，具有较强的团队合作、学习进步、交流表达的能力。</p>
        </div>
        <div class="content4">
          <p>请将个人简历和作品案例发送至邮箱：yao001@anlv365.com </p>
          <p>联系电话：400-888-8888</p>
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
  width: 960px;
  
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
.title2{
  margin-top: 10px;
  font-size:30px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(0,0,0,1);
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
  justify-content: space-between;
  margin-top: 20px;
  font-size: 16px;
  padding-bottom: 10px;
  font-size:18px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(153,153,153,1);
  border-bottom: 1px solid rgba(204,204,204,1);
}
.content3 h3{
font-size:24px;
font-family:MicrosoftYaHei;
font-weight:400;
color:rgba(51,51,51,1);
line-height:60px;
}
.content3 p{
  font-size:16px;
font-family:MicrosoftYaHei;
font-weight:400;
color:rgba(102,102,102,1);
line-height:30px;
}
.content4{
width:960px;
height:106px;
background:rgba(242,243,244,1);
margin: 40px 0;
display: flex;
flex-direction: column;
justify-content: center;
align-items: flex-start;
}
.content4 p {
font-size:20px;
font-family:MicrosoftYaHei;
font-weight:400;
color:rgba(51,51,51,1);
line-height:30px;
margin-left: 50px
}
.top-img{
  width:100%;
}

@media screen and (max-width:1200px){
.main{
   width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: calc(100vh - 547px);
}  
}
</style>
