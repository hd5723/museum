<template>
  <div id="main" style="">
    <el-container>
      <!-- 顶栏容器 -->
      <el-header style="margin-top: 10px;">
        <el-menu
            :default-active="1"
            class="el-menu-demo"
            mode="horizontal"
            active-text-color="#409eff"
            router
            :collapse="false"
        >
          <div class="logo" style="width: 10%;" >
            <router-link to="/">
              <span style="width: 240px; position: absolute; top: 20px; left: 60px; ">罗刹海市博物馆</span>
              <img  src="./assets/logo.png" style="height: 50px;" alt />
            </router-link>
          </div>
          <el-menu-item index="/" >首页</el-menu-item>
          <el-sub-menu index="/about" >
            <template #title>关于我们</template>
            <el-menu-item index="/about/gk">概況</el-menu-item>
            <el-menu-item index="/about/ls">历史</el-menu-item>
            <el-menu-item index="/about/zjjs">专家介绍</el-menu-item>
            <el-menu-item index="/about/yzzc">院长致辞</el-menu-item>
            <el-menu-item index="/about/mhgs">幕后故事</el-menu-item>
            <el-menu-item index="/about/bwgzy">博物馆之友</el-menu-item>
            <el-menu-item index="/about/xwzx">新闻资讯</el-menu-item>
          </el-sub-menu>

          <el-menu-item index="/clzl">陈列展览</el-menu-item>
          <el-menu-item index="/sc">收藏</el-menu-item>
          <el-menu-item index="/cg">参观</el-menu-item>
          <el-menu-item index="/hd" > <template #title>活动</template></el-menu-item>
          <el-menu-item index="/xx" >学习</el-menu-item>
          <el-menu-item index="/yj" >研究</el-menu-item>
        </el-menu>
      </el-header>

      <!-- 主要区域容器 -->
      <el-main>
        <keep-alive>
          <router-view :key="$route.path+$route.query"></router-view>
        </keep-alive>
      </el-main>

      <!-- 底栏容器 -->
      <el-footer>
        <div class="footer">
          <el-row :gutter="25">

            <el-col :span="6" >
              <div style="width: 100%; color: #c6cbd1; margin: 25px 10px; font-size: 20px"> 服务热线 </div>
              <div style="color: #14cb85; font-size: 18px">
                <span> <el-icon color="#14cb85"> <phone /> </el-icon>  13999999999</span>
              </div>
              <div style="width: 100%; color: #b0b0b0; margin: 25px 10px"> 深圳市XXXX </div>
              <div style="width: 100%; color: #b0b0b0; margin: 25px 10px"> 邮编：XXXXX</div>
            </el-col>


            <el-col :span="6" >
              <div style="width: 100%; color: #c6cbd1; margin: 25px 10px; font-size: 20px"> 新闻资讯 </div>
              <div style="width: 100%; color: #b0b0b0; margin: 25px 10px"> <router-link to="/news" style="color: #6a737d;font-size: 17px ">博物馆新闻</router-link>  </div>
              <div style="width: 100%; color: #b0b0b0; margin: 25px 10px"> <router-link to="/news" style="color: #6a737d;font-size: 17px ">行业动态</router-link>  </div>
            </el-col>

            <el-col :span="6" >
              <div style="width: 100%; color: #c6cbd1; margin: 25px 10px; font-size: 20px"> 关于 </div>
              <div style="width: 100%; margin: 25px 10px">  <router-link to="/about" style="color: #6a737d;font-size: 17px ">关于我们</router-link> </div>
            </el-col>
          </el-row>

          <div class="mod_help">
            <p class="coty">博物馆版权所有 &copy; 2012-2021 XXXX</p>
          </div>

        </div>
      </el-footer>
      <!-- 底栏容器END -->
    </el-container>
  </div>
</template>



<script>

export default {
  name: 'App',
  components: {
  }
}
</script>


<style>
/* 全局CSS */
#app {
  padding: 0;
  margin: 0;
  border: 0;
  list-style: none;
}

#app .el-header {
  padding: 0;
}
#app .el-main {
  min-height: 300px;
  padding: 20px 0;
}
#app .el-footer {
  padding: 0;
}

#main{
  background: #ffffff url('./assets/imgs/home/bg.jpg') repeat 0 0
}

a,
a:hover {
  text-decoration: none;
}
/* 全局CSS END */

/* 顶部导航栏CSS */
.topbar {
  height: 40px;
  background-color: #3d3d3d;
  margin-bottom: 20px;
}
.topbar .nav {
  width: 1225px;
  margin: 0 auto;
}
.topbar .nav ul {
  float: right;
}
.topbar .nav li {
  float: left;
  height: 40px;
  color: #b0b0b0;
  font-size: 14px;
  text-align: center;
  line-height: 40px;
  margin-left: 20px;
}
.topbar .nav .sep {
  color: #b0b0b0;
  font-size: 12px;
  margin: 0 5px;
}
.topbar .nav li .el-button {
  color: #b0b0b0;
}
.topbar .nav .el-button:hover {
  color: #fff;
}
.topbar .nav li a {
  color: #b0b0b0;
}
.topbar .nav a:hover {
  color: #fff;
}
.topbar .nav .shopCart {
  width: 120px;
  background: #424242;
}
.topbar .nav .shopCart:hover {
  background: #fff;
}
.topbar .nav .shopCart:hover a {
  color: #ff6700;
}
.topbar .nav .shopCart-full {
  width: 120px;
  background: #ff6700;
}
.topbar .nav .shopCart-full a {
  color: white;
}
/* 顶部导航栏CSS END */

/* 顶栏容器CSS */
.el-header .el-menu {
  max-width: 1225px;
  margin: 0 auto;
}
.el-header .logo {
  height: 60px;
  width: 339px;
  float: left;
  margin-right: 100px;
  position: relative;
}
.el-header .so {
  margin-top: 10px;
  width: 300px;
  position: absolute;
  right: 1%;

}
/* 顶栏容器CSS END */

/* 底栏容器CSS */
.footer {
  width: 100%;
  text-align: center;
  background: #2f2f2f;
  padding-bottom: 20px;
}
.footer .ng-promise-box {
  border-bottom: 1px solid #3d3d3d;
  line-height: 145px;
}
.footer .ng-promise-box {
  margin: 0 auto;
  border-bottom: 1px solid #3d3d3d;
  line-height: 145px;
}
.footer .ng-promise-box .ng-promise p a {
  color: #fff;
  font-size: 20px;
  margin-right: 210px;
  padding-left: 44px;
  height: 40px;
  display: inline-block;
  line-height: 40px;
  text-decoration: none;
  background: url("assets/imgs/us-icon.png") no-repeat left 0;
}
.footer .github {
  height: 50px;
  line-height: 50px;
  margin-top: 20px;
}
.footer .github .github-but {
  width: 50px;
  height: 50px;
  margin: 0 auto;
  background: url("assets/imgs/github.png") no-repeat;
}
.footer .mod_help {
  text-align: center;
  color: #888888;
}
.footer .mod_help p {
  margin: 20px 0 16px 0;
}

.footer .mod_help p a {
  color: #888888;
  text-decoration: none;
}
.footer .mod_help p a:hover {
  color: #fff;
}
.footer .mod_help p span {
  padding: 0 22px;
}
/* 底栏容器CSS END */

.flex-grow {
  flex-grow: 1;
}

li.el-menu-item{
  font-size: 18px;
}
div.el-sub-menu__title {
  font-size: 18px;
}

</style>

