
<template>
 <div class="box">
   <h1>todolist</h1>
   <div>
     <input type="text" v-model="name" placeholder="请输入你的任务名称">
   </div>
   <div >
     <h3>吃饭 <input type="checkbox" v-model="checked"></h3>
     <h3>睡觉 <input type="checkbox" v-model="checked"></h3>
     <h3>敲代码 <input type="checkbox" v-model="checked"></h3>
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
</style>