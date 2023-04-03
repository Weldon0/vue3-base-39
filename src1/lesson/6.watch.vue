<template>
  <div></div>
</template>

<script setup>
import { reactive, ref, watch } from "vue";

const userInfo = reactive({
  userName: "黑马",
  age: 18,
  message: {
    info: "你好",
  },
});

const count = ref(3000);

// 1、使用watch监听单个响应式数据的变化
// watch(userInfo, (newUserInfo) => {
//   console.log(newUserInfo);
// });
//
setTimeout(() => {
  userInfo.userName = "传智";
}, 1000);
//
// setTimeout(() => {
//   count.value = 200;
// }, 2000);
//
// // 2、监听多个响应式数据
// watch([count, userInfo], (newData, oldData, onCleanup) => {
//   // newData最新的数据，数组格式[],监听的数据的顺序一致
//   // oldData变化之前的数据，数组格式，监听的数据的顺序一致
//   console.log(newData[1].userName);
//   console.log(newData[0]);
// });

// 3、监听对象中某一个属性【基本值】的变化,如果是简单数据类型，必须通过函数的形式进行返回
// watch(
//   () => userInfo.userName,
//   (newUserName) => {
//     console.log(newUserName);
//   }
// );

// 4、监听数据对象中的复杂数据类型的变化
// 监听的属性是复杂数据类型，只有把监听的对象替换了之后，才可以监听到变化
// 里面的属性修改了之后，默认是不会触发更新的
watch(
  () => userInfo.message,
  (newMessage) => {
    console.log(newMessage);
  },
  {
    deep: true, // 开启深度监听
    immediate: true, // 立即执行
  }
);

setTimeout(() => {
  userInfo.message.info = "new Message";
}, 1000);
</script>

<style lang="scss" scoped></style>
