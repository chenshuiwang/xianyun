<template>
  <div>
    <!-- 轮播图 -->
    <el-carousel class="carousel" height="700px">
      <el-carousel-item v-for="(item,index) in banners" :key="index">
        <div class="banner" :style="`background:url(${item}) center center no-repeat`"></div>
      </el-carousel-item>
    </el-carousel>
  </div>
</template>

<script>
export default {
  data() {
    return {
      banners: [
        "http://157.122.54.189:9095/assets/images/th01.jfif",
        "http://157.122.54.189:9095/assets/images/th02.jfif"
      ]
    };
  }
};
</script>

<style lang='less' scoped>
.carousel{
    //width: 1000px;

}
.banner{
    height: 700px;
    width: 100%;
}
</style>