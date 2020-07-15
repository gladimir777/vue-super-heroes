<template>
  <div>
    <input
      type="text"
      v-model="name"
      placeholder="Buscar.."
      @input="handleSearch"
    />
  </div>
</template>

<script>
export default {
  name: "Search",

  data: () => {
    return {
      name: "",
    };
  },

  methods: {
    handleSearch() {
      console.log("test", this.name);

      this.$emit("search-heroe", this.name);
    },
  },
};
</script>

<style scoped>
input[type="text"] {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}
</style>
