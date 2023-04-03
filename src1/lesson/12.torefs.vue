<template>
  <div>
    <h1>{{ name }}</h1>
    <button @click="name = 'abc'">修改name</button>
  </div>
</template>

<script setup>
import { reactive, toRef } from "vue";

// 响应式数据解构出来以后，丢失响应式, 如果想要保持响应式，可以使用toRefs
// toRefs:
const userInfo = reactive({
  name: "John",
  age: 20,
  address: "USA",
});
// userInfo.age = 23;

function toRefs(object) {
  const ret = Array.isArray(object) ? new Array(object.length) : {};
  for (const key in object) {
    ret[key] = toRef(object, key);
  }
  return ret;
}

// toRefs:把整个对象遍历处理成ref响应式
// toRefs底层也是遍历对象，把每一个对象处理成toRef的响应式
// debugger;
const res = toRefs(userInfo);
console.log(res);
// 处理单个数据
const age = toRef(userInfo, "age");
// debugger;
console.log(age);
//
// 遍历对象里面的所有属性，把属性变成ref类型
// console.log(name.value);
</script>

<style lang="scss" scoped></style>
