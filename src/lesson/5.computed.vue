<template>
  <div>
    <div v-for="item in betterScoreList" :key="item">
      {{ item }}
    </div>
    <button @click="pushScore">修改数值</button>
  </div>
</template>

<script setup>
// 计算属性：根据已有的状态，派生出一个新的状态
// 具有缓存的特点：如果依赖的项，没有发生变化，不管当前的值使用多少次，不会重新计算，而是使用缓存的结果。
import { computed, ref } from "vue";
// 原有的分数列表
// 需求：界面上展示分数高于90的分数
const scoreList = ref([4, 6, 7, 78, 45, 96, 99, 91]);
// 可写的计算属性
const betterScoreList = computed({
  get() {
    return scoreList.value.filter((item) => item > 90);
  },
  // 设置当前属性的时候会触发
  set(newValue) {
    console.log(newValue);
  },
});

const pushScore = () => {
  scoreList.value.push(200);
};
</script>

<style lang="scss" scoped></style>
