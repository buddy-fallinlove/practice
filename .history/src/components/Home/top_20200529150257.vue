<template>
 <div>
   <input type="text" v-model="title" @keydown.enter="enter">
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
       title: ''
     }
   },
   methods: {
     enter() {
       let flag = true
       this.todos.map(item => {
         if(item.title === this.title) {
           flag = false
           alert('请勿重复添加任务')
         }
       })
       if(flag) {
         let obj = {
           title: this.title,
           complete: false
         }
         this.$emit(add,obj)
       }
     }
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