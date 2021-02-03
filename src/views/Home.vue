<template>
  <!--onselectstart="return false" -->
  <div class="container">
    <div class="Tabbar">
      <Header></Header>
    </div>
    <div class="home">
      <RouterView />
    </div>
  </div>
</template>

<script lang="ts">
import Header from "../components/head/Header2.vue";

import { defineComponent } from "vue";
export default defineComponent({
  components: {
    Header,
  },
});
</script>

<style lang="less" scoped>
.container {
  // background-color: #acbcd6;
  position: absolute;
  width: 100%;
  height: 100%;
  // background-color: #121c30;

  .Tabbar {
    position: fixed;
    top: 0;
    width: 100%;
    height: 60px;
    // line-height: 100px;
    background-color: #fff;
    box-shadow: 0px 3px 3px #20b2aa;
    z-index: 10;
  }

  .home {
    width: 100%;
    height: 85%;
    margin-top: 100px;
    z-index: 1;
  }

  .footter {
    width: 100%;
    height: 20px;
    //     background: #5b6d81;
    line-height: 20px;
    text-align: center;
    /* 方法一 */
    position: fixed;
    bottom: 0;
  }
}
</style>
