<template>
  <div>
    <div v-for="(todo, index) in todos" :key="index">
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template>

<script>
import TodoItem from "../components/TodoItem";

export default {
  name: "Todos",
  props: ["todos"],
  components: {
    TodoItem,
  },
};
</script>

<style lang="stylus" scoped></style>
