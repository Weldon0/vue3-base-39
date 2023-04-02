<template>
  <div>{{ count }}</div>
  <button @click="addCount">点击自增</button>
</template>

<script setup>
// setup语法糖，script标签上设置setup属性
import { ref } from "vue";

const count = ref(0);
const addCount = () => {
  count.value++;
};
</script>

<!--<script>-->
<!--import { ref } from "vue";-->

<!--export default {-->
<!--  setup() {-->
<!--    const count = ref(0);-->
<!--    const addCount = () => {-->
<!--      count.value++;-->
<!--    };-->

<!--    return {-->
<!--      count,-->
<!--      addCount,-->
<!--    };-->
<!--  },-->
<!--};-->
<!--</script>-->
