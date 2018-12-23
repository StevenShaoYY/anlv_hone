<template lang="html">
  <header>
    <div class="w960">
      <div class="header-pic"></div>
      <ul class="menu-container">
        <div class="menu-div" v-for="(item, index) in routerConfig" :key="index" >
          <li class="menu-item" v-if="!item.child" @click="goTo(item.path)" :class="{'active':item.code==active}">
            {{item.name}}
          </li>
          <li class="menu-item dropdown" v-if="item.child" :class="{'active':item.code[0]==active[0]}">
            {{item.name}}
            <ul class="submenu-container"  v-if="item.child">
              <li class="submenu-item" v-for="(itemm, indexx) in item.child" :key="indexx"  @click="goTo(itemm.path)" :class="{'active':itemm.code==active}">
                {{itemm.name}}
              </li>
            </ul>
          </li>
        </div>  
      </ul>
    </div>
  </header>
</template>

<script>
import 'normalize.css'
export default {
  props:{
    active: {
      type: String,
      default: '1'
    }
  },
  data() {
    return {
      routerConfig: [
        {
          name: '首页',
          path: 'index.html',
          code: '1'
        },
        {
          name: '产品中心',
          path: 'product.html',
          code: '2'
        },
        {
          name: '解决方案',
          path: 'fixplan1.html',
          code: '3-1',
          child: [
            {
              name: '旅业治安登记互联网方案',
              path: 'fixplan1.html',
              code: '3-1'
            },
            {
              name: '安全终端开放服务接入方案',
              path: 'fixplan2.html',
              code: '3-2'
            }
          ]
        },
        {
          name: '服务支持',
          path: 'usebook.html',
          code: '4-1',
          child: [
            {
              name: '使用手册',
              path: 'usebook.html',
              code: '4-1'
            },
            {
              name: '开放平台',
              path: 'openplan.html',
              code: '4-2'
            },
            {
              name: '下载中心',
              path: 'downloadcenter.html',
              code: '4-3'
            },
            {
              name: '联系我们',
              path: 'concatus.html',
              code: '4-4'
            }
          ]
        },
        {
          name: '案例分享',
          path: 'caseshare.html',
          code: '5'
        },
        {
          name: '合作伙伴',
          path: 'panter.html',
          code: '6'
        },
        {
          name: '关于安旅',
          path: 'aboutAnlv.html',
          code: '7-1',
          child: [
            {
              name: '安旅介绍',
              path: 'aboutAnlv.html',
              code: '7-1'
            },
            {
              name: '加入安旅',
              path: 'addAnlv.html',
              code: '7-2'
            }
          ]
        }
      ]
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
  header {
    width: 100%;
    display: flex;
    justify-content: center;
  }
  .w960 {
    width: 1200px;
    height: 63px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }
  .w960 .header-pic {
    width: 260px;
    background:transparent url('../assets/sy_icon.png') no-repeat;
    background-position:-291px -623px;
  }
  .w960 .menu-container{
    display: flex;
    flex-direction: row;
    list-style:none
  }
  .w960 .menu-item{
    height: 63px;
    font-size:17px;
    font-weight:400;
    color:rgba(0,0,0,1);
    line-height: 63px;
    padding: 0 15px;
    cursor: pointer;
  } 
  .w960 .submenu-container{
      display: none;
      position: absolute;
      background-color: #f9f9f9;
      min-width: 160px;
      box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
      z-index: 1;
      color:rgba(0,0,0,1);
  }
  .w960 .submenu-container .submenu-item{
      color:rgba(0,0,0,1);
      padding: 0 40px;
  }
  .menu-item:hover {
    background-color:#FF961A;
  }
  .active {
    background-color:#FF961A;
  }
  .dropdown:hover .submenu-container {
    display: block;
    z-index: 20;
  }
  .submenu-container .submenu-item:hover{
    background-color:#FF961A;
  }
</style>
