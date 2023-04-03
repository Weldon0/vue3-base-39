<script setup>
import { ref } from "vue";
import TodoHeader from "./components/TodoHeader.vue";
import TodoMain from "./components/TodoMain.vue";
import TodoFooter from "./components/TodoFooter.vue";
// 提供数据
const list = ref([
  {
    id: 1,
    name: "吃饭",
    done: true,
  },
  {
    id: 2,
    name: "睡觉",
    done: false,
  },
  {
    id: 3,
    name: "打豆豆",
    done: false,
  },
]);
</script>

<template>
  <section class="todoapp">
    <TodoHeader></TodoHeader>
    <TodoMain :list="list"></TodoMain>
    <TodoFooter></TodoFooter>
  </section>
</template>

<style></style>
