<template>
  <div>
    <h1 ref="hello">你好</h1>
    <button @click="changeCount">+1</button>
  </div>
</template>

<script setup>
import {
  onActivated,
  onBeforeMount,
  onBeforeUnmount,
  onBeforeUpdate,
  onDeactivated,
  onMounted,
  onUnmounted,
  onUpdated,
  ref,
} from "vue";
const count = ref(0);
const changeCount = () => {
  count.value++;
};

// 注册回调的形式，处理生命周期钩子
onBeforeMount(() => {
  console.log("onBeforeMount");
});
onMounted(() => {
  console.log("onMounted");
  //   初始化图表的时候，通过原生的dom元素进行初始化的，所以在onMounted中进行初始化
});
onBeforeUpdate(() => {
  console.log("onBeforeUpdate");
});
onUpdated(() => {
  console.log("onUpdated");
});
onBeforeUnmount(() => {
  console.log("onBeforeUnmount");
});
onUnmounted(() => {
  console.log("onUnmounted");
});
onActivated(() => {
  console.log("onActivated");
}); // keep-alive之后的生命周期
onDeactivated(() => {
  console.log("onDeactivated");
});
</script>

<style lang="scss" scoped></style>
