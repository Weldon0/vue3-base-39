<template>
  <div>
    <ref-test ref="test" />
    <button @click="getComponentInstance">获取组件的实例</button>
  </div>
</template>

<script setup>
// 1、vue2里面给组件添加ref，可以获取到组件内部的所有属性或者方法
// 2、setup语法糖里面的ref，只能获取到组件内部通过defineExpose暴漏出来的属性或者方法
import RefTest from "../components/ref-test.vue";
import { ref } from "vue";

const test = ref(null);
const getComponentInstance = () => {
  console.log(test.value.count);
};
</script>

<style lang="scss" scoped></style>
