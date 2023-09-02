<template>
  <div class="main-box">
    <div class="main">
      <!-- 轮播图 -->
      <div class="block">
        <el-carousel :interval="4000"  height="600px"  >
          <el-carousel-item v-for="item in carouseData" :key="item">
            <div class="pic_item">
              <img :src="item.picture" style="width: 100%;height: 600px;" alt=""/>
              <span class="title">{{item.title}}</span>
              <span class="subTitle">{{item.subTitle}}</span>
            </div>
          </el-carousel-item>
        </el-carousel>
      </div>
      <!-- 轮播图END -->

      <!-- 经典产品  -->
      <div style="text-align: center;margin: 60px 2px 20px 2px">
        <h1>主題收藏</h1>
<!--        <div style="margin: 20px 0 ; color: #6a737d">
          <h3>我们的产品后端主要基于Java+Mysql+Redis+SpringCloud alibaba技术实现，前端使用了Vue3、Router、Axios、Echarts等技术</h3>
        </div>-->

        <!-- 项目介绍 Tab -->
        <div style="margin: 20px 0; text-align: left; ">
          <el-tabs tab-position="bottom" type="border-card"  class="demo-tabs" >
            <el-tab-pane v-for="item in carouseProjectData" :label="item.subTitle" >
              <el-row :gutter="20">
                <el-col :span="12"> <img :src="item.picture" style="width: 100%;height: 400px;" alt=""/></el-col>
                <el-col :span="12">
                  <div class="title">{{item.title}}</div>
                  <div class="subTitle"><p v-html="item.content"> </p></div>
                </el-col>
              </el-row>
            </el-tab-pane>
          </el-tabs>
        </div>

      </div>
      <!-- 经典产品END -->

      <!-- 新闻动态  -->
      <div style="text-align: center;margin: 60px 2px 20px 2px">
        <h1>馆藏国宝</h1>
<!--        <div style="margin: 20px 0; color: #6a737d">
          <h3>公司近期新闻动态，行业热点资讯</h3>
        </div>-->

        <!-- 新闻动态 内容区域 -->
        <div class="flex" style="margin: 20px 0; position: relative; " >
          <el-row :gutter="20">
            <el-col :span="12" style="position: relative; ">
              <div style="width: 100%; position: relative; " v-for="item in newList.slice(0,1)">
                <div class="pic_item" style="position: relative; ">
                  <img :src="item.picture" style="width: 100%;height: 400px;" alt=""/>
                </div>
                <div class="pic_title_bottom">{{item.title}}</div>
              </div>
            </el-col>
            <el-col :span="6" style="position: relative; ">
              <div style="width: 100%; position: relative;" v-for="item in newList.slice(1,3)">
                <div class="pic_item" style="position: relative; ">
                  <img :src="item.picture" style="width: 100%;height: 200px;" alt=""/>
                </div>
                <span class="pic_title_bottom" style="z-index: 2">{{item.title}}</span>
              </div>
            </el-col>
            <el-col :span="6" style="position: relative; ">
              <div style="width: 100%; position: relative; " v-for="item in newList.slice(3,5)">
                <div class="pic_item" style="position: relative; ">
                  <img :src="item.picture" style="width: 100%;height: 200px;" alt=""/>
                </div>
                <span class="pic_title_bottom">{{item.title}}</span>
              </div>
            </el-col>
          </el-row>
        </div>

        <p style="margin: 20px 0;">
          <router-link to="/news">
            <el-button type="success" style="width: 250px; line-height: 50px; height: 50px; ">
              查看更多 <el-icon><Right /></el-icon>
            </el-button>
          </router-link>
        </p>
      </div>
      <!-- 新闻动态END -->

    </div>
  </div>
</template>

<script>

import axios from "axios";

export default {
  name: 'VueHome',
  data() {
    return {
      carouseData : [],
      carouseProjectData: [],
      newList: "" , //新闻列表
    }
  },
  created() {
    //获取首页轮播图
    this.getData("carouseData" , "../../static/mock/carouse/data.json");

    //获取项目数据
    this.getData("carouseProjectData" , "../../static/mock/project/data.json" );

    //获取新闻数据
    this.getData("newList"  ,  "../../static/mock/news/data.json");

  },
  methods: {

    getData(val , url){
      axios.get( url ).then((response) => {
        this[val] = response.data.success.data;
      });
    },
  }
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "@/assets/css/index.css";

.pic_item span.title {
  position: absolute;
  left: 2rem;
  top: 2rem;
  color: snow;
  font-size: 40px;
}


.pic_title_bottom {
  position: absolute;
  color: snow;
  font-size: 18px;
  left: 1px;
  bottom: 7px;
  background: rgba(0,0,0,.5);
  line-height: 30px;
  text-align: left;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  width: 98%;
}

.pic_item span.subTitle {
  position: absolute;
  left: 2rem;
  top: 7rem;
  color: snow;
  font-size: 22px;
}

.title {
  left: 2rem;
  top: 2rem;
  color: #2f2f2f;
  font-size: 40px;
}

.subTitle {
  left: 2rem;
  top: 7rem;
  color: #2f2f2f;
  font-size: 16px;
}


</style>
