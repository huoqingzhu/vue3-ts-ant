<template >
  <div class="count">
    <span id="map">父组件：</span
    ><a-input v-model:value="value" style="width: 200px"></a-input>
    <child :onSubmit="onSubmit"></child>
  </div>
</template>
<script lang="ts">
import { defineComponent, onMounted, reactive, ref, toRefs } from "vue";
import child from "./child.vue";
export default defineComponent({
  components: {
    child,
  },
  setup(props, context) {
    console.log("change");
    const state = reactive({
      value: "初始值",
    });
    const onSubmit = () => {
      alert(state.value);
    };
    const dom = document.getElementById("map");
    console.log(dom);
    onMounted(() => {
      const dom = document.getElementById("map");
      console.log(dom);
    });
    return {
      ...toRefs(state), //将state解构成普通对象
      onSubmit,
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

