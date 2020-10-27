<template>
 <div>
    <div v-for="(item,index) in todos" :key="index">
      <input type="checkbox" v-model="item.complete"> {{item.title}}
    </div>
 </div>
</template>

<script>
 export default {
   name: '',
   props: {
     todos: {
       type: Array
     }
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

</style>