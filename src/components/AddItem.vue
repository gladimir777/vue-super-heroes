<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="" placeholder="Add todo ..." />
      <input type="submit" value="submit" />
    </form>
  </div>
</template>

<script>
export default {
  name: "AddItem",

  data() {
    return {
      title: "",
    };
  },

  methods: {
    addTodo(e) {
      e.preventDefault();
      const newItem = {
        title: this.title,
        completed: false,
        id: 3,
      };

      this.$emit("add-item", newItem);
      this.title = "";
    },
  },
};
</script>

<style scoped></style>
