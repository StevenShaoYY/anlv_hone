<template>
  <div id="app">
    <top-bar :active="'4-4'"></top-bar>
    <div class="map-container">
      <baidu-map class="map" ak="gZBDeShGPNDq7NRfKVRSoBDeXKnMlB2U"  :center="centerData" @ready="handler" :zoom="18">
        <bm-marker :position="centerData" animation="BMAP_ANIMATION_BOUNCE" size="50px">
          <!-- <bm-label content="我爱北京天安门" :labelStyle="{color: 'red', fontSize : '24px'}" /> -->
        </bm-marker>  
      </baidu-map> 
      <div class="shadow-back">
        <p>浙江省杭州市滨江区信诚路智汇中心A座1602室</p>
        <p>杭州安旅科技有限公司</p>
      </div>
    </div>
    <section class="main">
      <div class="main-c">
        <h3 class="title">联系我们</h3>
        <div class="content2">
          <p>地址：浙江省杭州市滨江区信诚路智汇中心A座1602室</p>
          <p>邮箱：public@anlv365.com</p>
          <p>电话：0571-88216684</p>
        </div>
      </div>
    </section>
    <bottom></bottom>
  </div>
</template>

<script>
import topBar from '../../components/header.vue'
import bottom from '../../components/bottom.vue'
import BaiduMap from 'vue-baidu-map/components/map/Map.vue'
import BmMarker from 'vue-baidu-map/components/overlays/Marker.vue'
export default {
  components: {
    topBar,
    bottom,
    BaiduMap,
    BmMarker
  },
  data() {
    return {
      centerData: {
        lng: 120.181084, 
        lat: 30.192501
      },
      // centerData: '杭州'
    }
  },
  created() {
  },
  mounted() {
    
  },
  methods: {
    handler ({BMap, map}) {
      console.log(BMap, map)
      
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
.map{
  width: 100%;
  height: 600px;
}
.map-container{
  position: relative;
}
.shadow-back{
  height:175px;
  width:100%;
  bottom: 0px;
  background:rgba(32,24,33,1);
  opacity:0.5;
  position: absolute;
  font-size:24px;
  font-family:MicrosoftYaHei;
  font-weight:400;
  color:rgba(255,255,255,1);
  line-height:40px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.main-c{
  width: 600px;
  
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
.content2 {
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-top: 30px;
  font-size: 16px;
  margin-bottom: 100px;
}
.content .box-item{
  width: 390px;
  height: 161px;
  border:1px solid rgba(204, 204, 204, 1)
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
