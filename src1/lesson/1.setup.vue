<template>
  <div>
    <h1>{{ msg }}</h1>
    <button @click="showMsg">打印msg</button>
  </div>
</template>

<script>
// 1、setup是在beforeCreate钩子之前执行的
// 2、this是undefined【基本上不适用this】【所见即所得】
// 4、直接定义变量，模板中使用需要在setup函数中返回
export default {
  beforeCreate() {
    console.log("beforeCreate");
  },
  setup() {
    const msg = "黑马";
    // 定义一个函数，函数触发的时候，打印一下msg
    const showMsg = () => {
      console.log(msg);
    };
    // console.log(this);
    return {
      msg,
      showMsg,
    };
  },
};
</script>

<style lang="scss" scoped></style>
