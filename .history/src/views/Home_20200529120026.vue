
<template>
 <div class="box">
   <h1>todolist</h1>
   <div>
     <input type="text" v-model="name" placeholder="请输入你的任务名称">
   </div>
   <div class="box1">
     <h3>吃饭 <input type="checkbox" v-model="checked"></h3>
     <h3>睡觉 <input type="checkbox" v-model="checked"></h3>
     <h3>敲代码 <input type="checkbox" v-model="checked"></h3>
   </div>
   <div class="box2">
     <h2>已完成/全部</h2>
   </div>
 </div>
</template>

<script>
 export default {
   name: '',
   props: {
   },
   components: {

   },
   data () {
     return {

     }
   },
   methods: {

   },
   mounted() {

   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>
.box {
  width: 1200px;
  height: 400px;
}
.box1 {
  width: 200px;
  height: 200px;
  background-color: rgb(170,170,170);
}
.box2 {
  width: 50px;
  height: 50px;
}
</style>