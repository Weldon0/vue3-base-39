<template>
  <div>
      <img v-if="flag" src="./assets/vue.svg" alt="">
      <button @click="toggleFlag">显示或者隐藏</button>

      <h1>{{count}}</h1>
      <button @click="addCount">点击自增</button>
  </div>
</template>

<script>

import {ref} from "vue";

export default {
  setup() {

    // 切换图片显示或者隐藏
    const flag = ref(true) // 切换的标识
    const toogleFlag = () => {
      flag.value = !flag.value
    }


    const count = ref(0)
    // 数字自增的逻辑
    const addCount = () => {
      count.value ++
    }

    return {
      flag,
      toogleFlag,
      count,
      addCount
    }
  }
}

// vue3里面可以完全写vue2
// options API
// export default {
//   data() {
//     return {
//       flag: true,
//       count: 0
//     }
//   },
//   computed: {},
//   watch: {},
//   filters: {},
//   directives: {},
//   mixins: [],
//   props: [],
//   methods: {
//     toggleFlag() {
//       this.flag = !this.flag
//     },
//     addCount() {
//       this.count ++
//     }
//   },
// }
</script>
