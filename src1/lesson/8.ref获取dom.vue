<template>
  <div>
    <h1 ref="hello">你好</h1>
    <button @click="getHello">获取dom元素</button>
  </div>
</template>

<script setup>
// 如何通过ref获取dom元素？
// 1、标签绑定ref属性
// 2、在setup中定义和ref属性同名的变量
// 3、在setup中通过变量.value获取dom元素
import { ref } from "vue";

const hello = ref(null);
const getHello = () => {
  console.log((hello.value.innerHTML = "黑马"));
};
</script>

<style lang="scss" scoped></style>
