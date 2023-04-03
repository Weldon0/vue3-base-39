<template>
  <div>
    {{ count }}
  </div>
</template>

<script setup>
import { ref } from "vue";

const count = ref(0);

const addCount = () => {
  count.value++;
};

// 主动把组件内部的属性或者方法暴漏出去，提供给父组件使用
// defineExpose不需要引入
defineExpose({
  addCount,
  count,
});
</script>

<style lang="scss" scoped></style>
