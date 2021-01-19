<template>
  <div class="Home">
    <!-- <Count :countParent="10"></Count>
    <Count2 :countParent="10"></Count2>
    <watchs :countParent="10"></watchs> -->
    <moving></moving>
    <moving2></moving2>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import Count from "./page/count.vue";
import Count2 from "./page/count2.vue";
import watchs from "./page/watch.vue";
import moving from "./page/moving.vue";
import moving2 from "./page/moving2.vue";
export default defineComponent({
  components: {
    Count,
    Count2,
    watchs,
    moving,
    moving2,
  },
  setup() {},
});
</script>

<style lang="less" scoped>
.Home {
  height: 100%;
  width: 100%;
  // text-align: center;
}
</style>
