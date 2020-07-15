<template>
  <div class="super-heroe-container">
    <Header />
    <Heroes v-bind:heroes="heroes" />
  </div>
</template>

<script>
import Header from "./Header";
import Heroes from "./Heroes";
export default {
  name: "SuperHeroes",
  components: {
    Header,
    Heroes,
  },
  props: ["heroes"],
};
</script>

<style scoped>
.super-heroe-container {
  border: 2px solid #f0f0f0;
  border-radius: 5px;
}
</style>
