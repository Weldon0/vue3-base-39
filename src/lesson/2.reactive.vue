<template>
  <div>
    {{ obj.count }}
    <button @click="addCount">自增</button>
  </div>
</template>

<script>
// 1、reactive函数构建响应式数据的
// 2、reactive函数只接受{}/[]
// 3、proxy构建响应式
import { reactive } from "vue";

export default {
  setup() {
    // 数字的自增逻辑
    const obj = reactive({
      count: 0,
    });

    const addCount = () => {
      obj.count++;
    };
    return {
      obj,
      addCount,
    };
  },
};
</script>

<style lang="scss" scoped></style>
