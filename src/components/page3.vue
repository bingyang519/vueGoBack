<template>
  <div class="page3">
    <button @click="goBack">返回</button>
    <p>{{msg}}</p>
    <p>{{str}}</p>
  </div>
</template>

<script>
export default {
  name: "page3",
  data() {
    return {
	  msg: "我是第三个页面",
	  str:''
    };
  },
  methods: {
    getData() {
        console.warn('我调用第三个页面getData方法了')
        this.str= "我是通过调用方法加载的数据。。。";
    },
    goBack(){
        this.$router.go(-1)
    }
  },
  beforeRouteEnter(to, from, next){
      console.log('我是第三个页面的beforeRouteEnter方法')
      next()
  },
  created(){
	  console.log('我是第三个页面的 created 方法')
  },
  mounted(){
	  this.getData()
	  console.log('我是第三个页面的 mounted 方法')
  },
  activated(){
	  console.log('我是第三个页面的 activated 方法')
  },
  deactivated(){
	  console.log('我是第三个页面的 deactivated 方法')
  },
  destroyed(){
	  console.log('我是第三个页面的 destroyed 方法')
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
