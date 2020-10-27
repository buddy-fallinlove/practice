<template>
<div class="container">
  <div v-if="todos.length > 0">
    <div class="item" v-for="(item, index) in todos" :key="item.id" @mouseenter="enter(item, index)" @mouseleave="leave(item)">
      <div :class="{ active: activeIndex === index }">
        <input type="checkbox" v-model="item.complete" /> {{ item.title }}
        <button @click="del(item, index)" v-if="item.flag">删除</button>
      </div>
    </div>
  </div>
  <div v-else>暂无数据</div>
</div>
</template>

<script>
export default {
  name: "",
  props: {
    todos: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      activeIndex: -1,
    };
  },
  components: {},
  methods: {
    enter(item, index) {
      item.flag = true;
      this.activeIndex = index;
    },
    leave(item) {
      item.flag = false;
      this.activeIndex = -1;
    },
    del(item, index) {
      this.$emit("del", index);
    },
  },
  mounted() {
    this.todos.map((item, index) => {
      this.$set(item, "id", index + 1);
      this.$set(item, "flag", false);
    });
  },
  computed: {},
  watch: {},
};
</script>

<style lang="scss" scoped>
.container {
  .item {
    height: 30px;
  }
}

.active {
  background: #ccc;
}
</style>
