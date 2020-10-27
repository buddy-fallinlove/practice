<template>
<div>
  已完成{{completedArr}} / 全部 {{todos.length}} <button v-if="completedArr > 0" @click="delAll">清除已完成</button>
</div>
</template>

<script>
export default {
  name: '',
  props: {
    todos: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {}
  },
  components: {},
  methods: {
    delAll() {
      let arr = []
      arr = this.todos.filter(item => {
        return !item.complete
      })
      this.$emit('delAll', arr)
    }
  },
  mounted() {},
  computed: {
    completedArr() {
      let arr = []
      arr = this.todos.filter(item => {
        return item.complete
      })
      return arr.length
    }
  },
  watch: {}
}
</script>

<style lang='scss' scoped>

</style>
