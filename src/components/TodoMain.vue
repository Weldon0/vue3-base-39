<script setup>
const props = defineProps({
  list: {
    type: Array,
    required: true,
  },
});
</script>

<template>
  <section class="main">
    <input id="toggle-all" class="toggle-all" type="checkbox" />
    <label for="toggle-all">Mark all as complete</label>
    <ul class="todo-list">
      <li class="completed" v-for="item in list" :key="item.id">
        <div class="view">
          <input class="toggle" type="checkbox" :checked="item.done" />
          <label>{{ item.name }}</label>
          <button class="destroy"></button>
        </div>
        <input class="edit" value="Create a TodoMVC template" />
      </li>
      <!-- <li>
        <div class="view">
          <input class="toggle" type="checkbox" />
          <label>Buy a unicorn</label>
          <button class="destroy"></button>
        </div>
        <input class="edit" value="Rule the web" />
      </li> -->
    </ul>
  </section>
</template>

<style lang="less" scoped></style>
