<template>
  <div class="moving">
    <!-- <img src="./img/lan.gif" class="imgs" ref="box1" alt="" /> -->

    <img src="./img/lan.gif" class="img1" alt="" />
    <img src="./img/lan.gif" class="img2" />
    <img src="./img/lan.gif" class="img3" alt="" />
    <img src="./img/lan.gif" class="img4" alt="" />
    <img src="./img/hong.gif" class="img5" alt="" />
    <img src="./img/lan.gif" class="img6" alt="" />
    <img src="./img/lan.gif" class="img7" alt="" />
    <!-- <template v-for="item in listData" :key="item.num">
      <img
        src="./img/lan.gif"
        alt=""
        :style="item.style"
        :ref="`box${item.num}`"
      />
    </template> -->
  </div>
</template>
<script lang="ts">
import { defineComponent, reactive, toRefs } from "vue";
interface state {
  listData: any[];
  box1: any;
  box2: any;
}
export default defineComponent({
  setup() {
    const state: state = reactive({
      listData: [],
      box1: null,
      box2: null,
    });
    for (let i = 1; i < 8; i++) {
      let obj = {
        num: 1,
        style: {
          width: "80px",
          height: "80px",
          margin: "0 10px",
        },
      };
      obj.num = i;
      obj.style.width = `${100 - Math.abs(4 - i) * 5}px`;
      obj.style.height = `${100 - Math.abs(4 - i) * 5}px`;
      state.listData.push(obj);
    }
    console.log(state.listData);
    function change() {
      console.log(state.box1.getBoundingClientRect());
      console.log(state.box2.getBoundingClientRect());
    }
    return {
      ...toRefs(state),
      change,
    };
  },
});
</script>
<style lang="less" scoped>
.moving {
  width: 100%;
  height: 200px;
  position: relative;
  background-color: rgb(33, 88, 63);
  // background-color: #ccc;
}

.img1 {
  width: 90px;
  height: 90px;
  position: absolute;
  animation-name: move1;
  animation-duration: 2s;
  animation-fill-mode: forwards;
  animation-iteration-count: infinite;
}
.img2 {
  width: 100px;
  height: 100px;
  position: absolute;
  margin-left: 90px;
  animation-name: move2;
  animation-duration: 2s;
  // animation-direction: reverse;
  animation-fill-mode: forwards;
  animation-iteration-count: infinite;
}
.img3 {
  width: 110px;
  height: 110px;
  position: absolute;
  margin-left: 190px;
  animation-name: move2;
  animation-duration: 2s;
  animation-fill-mode: forwards;
  animation-iteration-count: infinite;
}
.img4 {
  width: 120px;
  height: 120px;
  position: absolute;
  margin-left: 300px;
  animation-name: move2;
  animation-duration: 2s;
  animation-fill-mode: forwards;
  animation-iteration-count: infinite;
}
.img5 {
  width: 130px;
  height: 130px;
  position: absolute;
  margin-left: 420px;
  animation-name: move2;
  animation-duration: 2s;
  animation-fill-mode: forwards;
  animation-iteration-count: infinite;
}
.img6 {
  width: 120px;
  height: 120px;
  position: absolute;
  margin-left: 550px;
  animation-name: move2;
  animation-duration: 2s;
  animation-fill-mode: forwards;
  animation-iteration-count: infinite;
}
.img7 {
  width: 110px;
  height: 110px;
  position: absolute;
  margin-left: 670px;
  animation-name: move2;
  animation-duration: 2s;
  animation-fill-mode: forwards;
  animation-iteration-count: infinite;
}
@keyframes move1 {
  0% {
    top: 0;
    left: 0px;
  }
  100% {
    top: 0;
    left: 660px;
  }
}
@keyframes move2 {
  0% {
    top: 0;
    left: 0px;
  }
  100% {
    top: 0;
    left: -110px;
  }
}
</style>

