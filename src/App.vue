<template>
  <div id="app">
    <Alert v-bind:error="error" v-bind:msg="msg" />
    <Search v-on:search-heroe="handleSearch" />
    <SuperHeroes v-bind:heroes="heroes" />
  </div>
</template>

<script>
import axios from "axios";
import SuperHeroes from "./components/SuperHeroes";
import Alert from "./components/Alert";
import Search from "./components/Search";

export default {
  name: "App",
  components: {
    SuperHeroes,
    Alert,
    Search,
  },

  data: () => {
    return {
      heroes: [],
      error: false,
      msg: "",
    };
  },

  methods: {
    handleSearch(name) {
      const test = this.heroes.filter((item) =>
        item.nombre.name.toLowerCase().includes(name.toLowerCase())
      );
      this.heroes = test;
    },

    getHeroes() {
      axios
        .get(
          `http://157.245.138.232:9091/api/v1/test/superheroes/?puedeVolar =true`
        )
        .then((res) => res.data)
        .then((res) => {
          if (res.data.length == 0) {
            this.error = true;
            this.msg = `No hay datos`;
          }
          this.heroes = res.data;
        })
        .catch((err) => {
          console.log("Error", err);
          this.error = true;
          this.msg = `Erorr`;
          this.$emit("fetch-error", this.error);
        });
    },
    getHeroe(id) {
      axios
        .get(`http://157.245.138.232:9091/api/v1/test/superheroes/${id}`)
        .then((res) => res.data)
        .then((res) => {
          if (res.data.length == 0) {
            this.msg = `No encuentro El usuario id ${id}`;
            this.error = true;
            return;
          }
          this.heroes = [...this.heroes, res.data];
        })
        .catch((err) => {
          console.log("Error", err);
          this.error = true;
          this.msg = `Erorr`;
          this.$emit("fetch-error", this.error);
        });
    },
  },

  created() {
    this.getHeroes();
    this.getHeroe(1);
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  align-items: center;
  flex-direction: column;
}
</style>
