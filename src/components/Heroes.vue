<template>
  <div class="heroes-wrapper">
    <div class="heroes-container" v-for="(heroe, index) in heroes" :key="index">
      <Heroe v-bind:heroe="heroe" />
    </div>
  </div>
</template>

<script>
import Heroe from "./Heroe";
export default {
  name: "Heroes",
  components: {
    Heroe,
  },
  props: ["heroes"],
};
</script>

<style scoped></style>
