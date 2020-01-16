<template>
  <div>
    <Header></Header>
    <!-- <el-carousel class="carousel" height="700px">
      <el-carousel-item v-for="(item,index) in banners" :key="index">
        <div class="banner" :style="`background:url(${item}) center center no-repeat`"></div>
      </el-carousel-item>
    </el-carousel> -->
    <nuxt></nuxt>
    <Footer></Footer>
  </div>
</template>
<script>
import Header from "../components/header.vue";
import Footer from "../components/footer.vue";
export default {
  components: {
    Header,
    Footer
  },
};
</script>
<style>
* {
  padding: 0;
  margin: 0;
  text-decoration: none;
  list-style: none;
}
a {
  color: inherit;
}
a:hover {
  color: inherit;
}
.banner{
  width: 700px;
}
em,i{
  font-style: normal;
}
</style>
