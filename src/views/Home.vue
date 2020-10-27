<template>
<div>
  <!-- 使用组件 -->
  <!--  <child :msg='msg1' :num='num'></child>
  <child :msg='msg2' :num='num'></child> -->
  <!-- <child align='right'></child> -->
  <child :msg='msg1' :num.sync='num' @send='send' ref="child"></child>
  <br>
  <div ref="dv">123</div>
  <br>
  <div><button @click="update">改变子组件的值</button></div>
</div>
</template>

<script>
// 引入组件
import child from '../components/child/Child'

export default {
  name: '',
  props: {},
  data() {
    return {
      msg1: '我是父组件的信息1',
      msg2: '我是父组件的信息2',
      num: 10
    }
  },
  components: {
    // 注册组件
    child
  },
  methods: {
    send(val) {
      console.log(val)
    },
    update() {
      // this.$refs.child.n = 3
      this.$children[0].n = 3
      // console.log(this.$children)0
    }
  },
  // 生命周期
  // 创建前
  beforeCreate() {

  },
  // 已创建
  created() {

  },
  // 挂载前 
  beforeMount() {

  },
  // 已挂载
  mounted() {
    // 1. 数据初始化
    // 2. 发请求 在methods定义方法 在这调用
    // 如果要操作dom 最好加上this.$nextTick $nextTick能够保证拿到dom元素
    this.$nextTick(() => {
      console.log(this.$refs.dv)
    })
  },
  // 更新前 
  beforeUpdate() {

  },
  // 更新后
  updated() {

  },
  // 销毁前
  beforeDestroy() {
    // 清除页面当中的定时器
  },
  // 销毁后
  destroyed() {

  },
  computed: {},
  watch: {}
}
</script>

<style lang='scss' scoped>

</style>
