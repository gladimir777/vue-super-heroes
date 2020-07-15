<template>
  <div class="item" v-bind:class="{ 'is-complete': todo.completed }">
    <input type="checkbox" v-on:change="markComplete" />
    <p>{{ todo.title }}</p>
    <button @click="$emit('del-todo', todo.id)">x</button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],

  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.is-complete {
  background: red;
}

.item {
  display: flex;
}
</style>
