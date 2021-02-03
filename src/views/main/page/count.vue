<template >
  <div class="count">
    <h1>计数器组件ref</h1>
    <p>父组件传给我的值:{{ count }}</p>
    <a-button @click="add(20)" type="primary">+</a-button>
    <a-button @click="reduce(10)" type="primary">-</a-button>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from "vue";
import axios from "axios";

export default defineComponent({
  props: {
    countParent: {
      type: Number,
      default: 1,
    },
  },
  setup(props, context) {
    const count = ref(props.countParent);
    const add = (value: number) => {
      count.value = count.value + value;
    };
    console.log(window.location.origin + ":8085" + "/name");
    axios({
      method: "get",
      url: window.location.origin + ":8085" + "/name",
    })
      .then((res: any) => {
        console.log("请求成功");
      })
      .catch((err) => {
        console.log("请求失败");
      });
    const reduce = (value: number) => {
      count.value = count.value - value;
    };
    return {
      count,
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

