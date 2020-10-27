<template>
<div>
  <todo-header @add='add'></todo-header>
  <todo-main :todos='todos' @del='del'></todo-main>
  <todo-footer :todos='todos' @delAll='delAll'></todo-footer>
</div>
</template>

<script>
import todoHeader from '../components/todoHeader/todoHeader'
import todoMain from '../components/todoMain/todoMain'
import todoFooter from '../components/todoFooter/todoFooter'
export default {
  name: '',
  props: {},
  data() {
    return {
      todos: [{
          title: '吃饭',
          complete: false
        },
        {
          title: '睡觉',
          complete: false
        },
        {
          title: '敲代码',
          complete: true
        }
      ]
    }
  },
  components: {
    todoHeader,
    todoMain,
    todoFooter
  },
  methods: {
    add(val) {
      let flag = true
      this.todos.map(item => {
        if (item.title === val.title) {
          flag = false
          alert('任务已存在')
        }
      })
      if (flag) {
        this.todos.
        
        
        
        
        
        
        (val)
      }
    },
    del(index) {
      this.todos.splice(index, 1)
    },
    delAll(arr) {
      this.todos = arr
    }
  },
  mounted() {},
  computed: {},
  watch: {}
}
</script>

<style lang='scss' scoped>

</style>
