<template>
  <div class="Home">
    <Count :countParent="10"></Count>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import Count from "./page/count.vue";
export default defineComponent({
  components: {
    Count,
  },
  setup() {},
});
</script>

<style lang="less" scoped>
.Home {
  height: 100%;
  width: 100%;
  text-align: center;
}
</style>
