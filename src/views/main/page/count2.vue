<template >
  <div class="count">
    <h1>reactive</h1>
    <p>父组件传给我的值:{{ count }}</p>
    <p>{{ name }}</p>
    <a-button @click="add(20)" type="primary">+</a-button>
    <a-button @click="reduce(10)" type="primary">-</a-button>
  </div>
</template>
<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
export default defineComponent({
  props: {
    countParent: {
      type: Number,
      default: 1,
    },
  },
  setup(props, context) {
    const state = reactive({
      name: "计算",
      count: props.countParent,
    });
    const add = (value: number) => {
      state.count = state.count + value;
      state.name = "正在进行加法计算";
    };
    const reduce = (value: number) => {
      state.count = state.count - value;
      state.name = "正在进行减法";
    };
    return {
      ...toRefs(state), //将state解构成普通对象
      add,
      reduce,
    };
  },
});
</script>
<style lang="less" scoped>
.count {
  width: 100%;
  height: 200px;
  border: 3px solid #ccc;
}
</style>

