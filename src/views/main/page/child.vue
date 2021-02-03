<template >
  <div class="text">
    <span>子组件:{{ state.name }}</span>
    <a-button @click="change">点击弹出</a-button>
  </div>
</template>
<script setup="props" lang="ts">
import { reactive, toRefs, ref, onMounted } from "vue";
// 声明props
declare const props: {
  onSubmit: Function;
};
onMounted(() => {
  console.log("页面加载了");
});
// 导出reactive 对象 这里不能用toRef解构了
export const state = reactive({
  name: "我的名字",
});
export const color = ref("red");
export const change = () => {
  state.name = "我改变了";
  color.value = "pink";
  // props.onSubmit();
};
</script>
<style lang="less" vars="{ color }" >
.text {
  color: var(--color);
}
</style>

