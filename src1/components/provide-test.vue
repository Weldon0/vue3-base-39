<template>
  <div>
    <div>
      {{ count }}
    </div>
    <button @click="updateCount">修改数据</button>
  </div>
</template>

<script setup>
// 【provide：跨组件传值】
// provide: 父组件提供数据
// 参数：provide("key", value)
// inject: 子组件接收数据
// 参数：inject("key")
// 也可以传递方法，用于修改数据
import { inject } from "vue";

const count = inject("count");
const updateCount = inject("updateCount");
</script>

<style lang="scss" scoped></style>
