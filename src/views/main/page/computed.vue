<template>
  <div class="zhushi">
    <div class="title">一.计算属性传参数</div>
    {{ count }}
    <div>
      (1). 2.x写法（现在一样能用） computed: { test() { return function (value:
      any) { return `我是计算属性${value}`; }; } },
    </div>
    <div>
      (2.) setup写法: const setColor=computed(()=>{ return (value:any)=>{ return
      `${state.name}${value}` } })
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, toRefs, computed, reactive } from "vue";

export default defineComponent({
  setup(context, props) {
    // 声明一个计数器
    const state = reactive({
      count: 1,
    });
    return {
      ...toRefs(state),
    };
  },
});
</script>

<style lang="less" scoped>
.title {
  width: 100%;
  display: flex;
  justify-content: center;
  color: pink;
  font-size: 0.4rem;
}
</style>
