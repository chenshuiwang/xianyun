<template>
  <div>
     <div class="button">
       <span v-for="(item,index) in user" :key="index" @click="aa(index)">{{item.name}}</span>
     </div>
     <div class="content">
       <div class="xiaoming" v-if="current === 0" >{{user[current].age}}</div>
       <div class="merry" v-if="current === 1">{{user[current].age}}</div>
       <div class="rose" v-if="current === 2">{{user[current].age}}</div>
     </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      current:0,
      user:[
        {
          name:'xiaoming',
          age:'17'
        },
        {
          name:'merry',
          age:'18'
        },
        {
          name:'rose',
          age:'19'
        }
      ]
    }
  },
  methods:{
    aa(index){
      this.current = index;
      console.log(this.current)
    }
  }
}
</script>

<style lang='less' scoped>
.button{
  span{
    margin-right: 20px;
  }
}
</style>