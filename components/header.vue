<template>
  <div class="header-wrapper">
    <el-row class="header" justify="space-between" type="flex" align="middle">
      <div class="logo">
        <img src="/logo.jpg" alt />
      </div>
      <el-row class="nav" type="flex">
        <nuxt-link to="/">首页</nuxt-link>
        <nuxt-link to="/post">旅游攻略</nuxt-link>
        <nuxt-link to="/hotel">酒店</nuxt-link>
        <nuxt-link to="/air">国内机票</nuxt-link>
      </el-row>
      <div class="login">
        <nuxt-link to="/user/login">登录/注册</nuxt-link>
      </div>
    </el-row>
  </div>
</template>

<script>
export default {};
</script>

<style lang='less' scoped>
.header-wrapper {
  height: 60px;
  background: #fff;
  border-bottom: 5px solid #eee;
  box-shadow: 0 3px 2px #f6f6f6;
  min-width: 1000px;
  //position: relative;
  //z-index: 2;
}
.header {
  .logo {
    img {
      width: 156px;
      height: 42px;
      display: block;
    }
  }
  .nav {
    margin-left: 20px;
    flex: 1;
    a {
      display: block;
      height: 60px;
      line-height: 60px;
      box-sizing: border-box;
      padding: 0 20px;
      &:hover {
        color: #409eff;
        //background-color: #409eff;
        border-bottom: 5px solid #409eff;
      }
    }
    .nuxt-link-exact-active {
      background: #409eff;
      color: #fff;
      &:hover{
          color: #fff;
      }
    }
  }
}
</style>