<template>
<div class="box" :style='{textAlign: align}'>
  {{msg}} --- {{num}} --- {{n}}
  <button @click="updateProps">改变props当中的值</button>
  <button @click="send">传值给父组件</button>
</div>
</template>

<script>
export default {
  name: '',
  props: {
    // 接收父组件传递过来的数据
    msg: {
      // 数据类型
      type: String,
      // 如果父组件不传这个属性 就会找默认值
      // default: '我是默认值'
      // 是否必传
      // required: true
      // 验证函数 参数默认是传递过来的值
      // 返回一个布尔值
      // validator(val) {
      //   // 跑出错误
      //   throw new Error('传入的msg必须包含字符1')
      //   return val.includes('1')
      // }
    },
    num: {
      type: Number
    },
    align: {
      type: String,
      validator(val) {
        if (!['left', 'center', 'right'].includes(val)) {
          throw new Error('align只能是left, center, right 其中一个')
        }
        return true
      },
      default: 'left',
    }
  },
  data() {
    return {
      n: 100,
      info: '我是子组件的数据'
    }
  },
  components: {},
  methods: {
    updateProps() {
      // this.num = 30
      // $parent找到父组件的对象
      // this.$parent.num = 30

      // this.$emit('update:num', 30)
    },
    send() {
      // 传值给父组件
      // $emit是一个函数 里面传入两个参数 第一个是分发事件的名字 第二个是给父组件传递的值
      this.$emit('send', {
        info: this.info,
        n: this.n
      })
    }
  },
  mounted() {},
  computed: {},
  watch: {}
}
</script>

<style lang="scss" scoped>
.box {
  border: 1px solid red;
  width: 300px;
  height: 30px;
}
</style>
