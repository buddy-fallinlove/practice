<template>
<div>
  <input type="text" placeholder="请输入" v-model="value" @keydown.enter="add">
</div>
</template>

<script>
export default {
  name: '',
  props: {},
  data() {
    return {
      value: ''
    }
  },
  components: {},
  methods: {
    add() {
      this.$emit('add', {
        title: this.value,
        complete: false
      })
      this.value = ''
    }
  },
  mounted() {},
  computed: {},
  watch: {}
}
</script>

<style lang='scss' scoped>

</style>
