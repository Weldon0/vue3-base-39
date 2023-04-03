<template>
  <div>
    <provide-test />
  </div>
</template>

<script setup>
// 跨组件传值，provide提供的数据只有当前组件的后代组件才可以使用inject注入，再使用
import ProvideTest from "../components/provide-test.vue";
import { provide, ref } from "vue";

const count = ref(0);
const updateCount = () => {
  count.value++;
};

// provide暴漏出去
provide("count", count);
provide("updateCount", updateCount);
</script>

<style lang="scss" scoped></style>
