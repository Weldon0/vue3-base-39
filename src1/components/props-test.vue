<template>
  <div>
    {{ msg }}
    我是子组件 ==>
    {{ count }}
    <button @click="changeCount">修改父组件的count</button>
  </div>
</template>

<script setup>
// 父组件传递过来了一个方法叫做changeCount
// defineProps接收父组件传递过来的数据

// 如果js中用到父组件传递过来的值
// 1、接收过来的数据，可以直接在模板中使用
// 2、但是如果js里面要用到这些值，必须接收defineProps返回的结果
const props = defineProps({
  count: Number,
  msg: String,
});

console.log(props.count);
// 子组件接受事件
const emits = defineEmits(["changeCount"]);
// 使用deinfeEmits的返回值进行触发事件
const changeCount = () => {
  // this.$emit('事件名')
  emits("changeCount", 10);
};
</script>

<style lang="scss" scoped></style>
