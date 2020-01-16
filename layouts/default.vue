<template>
  <div>
    <Header></Header>
    <Footer></Footer>
  </div>
</template>
<script>
import Header from '../components/header.vue'
import Footer from '../components/footer.vue'
export default {
  components:{
    Header,Footer
  }
}
</script>
<style>
*{
    padding: 0;
    margin: 0;
    text-decoration: none;
    list-style: none;
}
a{
    color: inherit;
}
a:hover{
    color: inherit;
}

</style>
