<template>
  <div class="hero-container">
    <div class="avatar">
      <img v-bind:src="heroe.avatarURL" />
    </div>

    <div class="name-container">
      <span class="name">{{ heroe.nombre }}</span>
      <span class="real-name">{{ heroe.nombreReal }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Heroe",
  props: ["heroe"],
};
</script>

<style scoped>
.avatar img {
  height: 60px;
  width: 60px;
  border-radius: 50%;
  vertical-align: middle;
}

.hero-container {
  display: flex;
  border-top: 2px solid #f0f0f0;
  padding-bottom: 1rem;
  padding-top: 1rem;
  padding-left: 1rem;
}

.name-container {
  display: flex;
  flex-direction: column;
  margin-left: 4rem;
  margin-top: 0.2rem;
  width: 300px;
}

.name-container .name {
  font-size: 1.5rem;
}

.real-name {
  font-size: 0.8rem;
}
</style>
