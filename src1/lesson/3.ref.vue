<template>
  <div>
    {{ count }}
    <button @click="addCount">自增</button>
  </div>
</template>

<script>
// 1、ref是一个响应式的api
// 2、可以接受简单数据类型
// 3、接收的值包裹一个对象，真正的值在value上
// 4、修改ref定义的数据，js里面使用的时候通过value修改
// 5、模板里面不用.value,模板编译的时候，自动帮我们结构出来了
// 6、可不可以接收复杂数据类型
// 7、可以接受，也是使用value包裹
// 【总结】
// 1、简单数据类型只能使用ref，ref底层就是reactive，包裹一个对象之后构建响应式
// 2、复杂数据类型，ref和reactive都可以
import { ref } from "vue";

export default {
  setup() {
    // proxy构建响应式，对象或者数组，帮你包裹一个对象，才可以构建响应式
    // 推荐使用ref
    // ref底层也是使用reactive进行构建响应式
    const count = ref(1);
    console.log(count);
    const addCount = () => {
      count.value++;
    };

    // const list = ref([]);

    // const getList = async () => {
    //   const resList = await axios.get("https://localhost:80");
    //   list.value = resList;
    // };
    return {
      count,
      addCount,
    };
  },
};
</script>

<style lang="scss" scoped></style>
