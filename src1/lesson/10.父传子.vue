<template>
  <div>
    <props-test @changeCount="changeCount" :count="count" msg="黑马" />
  </div>
</template>

<script setup>
// 1、父组件通过自定义属性传递值
// 2、子组件使用defineProps接受值
import PropsTest from "../components/props-test.vue";
import { ref } from "vue";
const count = ref(0);
const changeCount = (num) => {
  count.value += num;
};
</script>

<style lang="scss" scoped></style>
