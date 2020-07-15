<template>
  <div class="alert" v-bind:class="{ 'error-msg': error }">
    <span class="closebtn" onclick="this.parentElement.style.display='none';"
      >&times;</span
    >
    <strong>Error!</strong>{{ msg }}!.
  </div>
</template>

<script>
export default {
  name: "Alert",
  props: ["error", "msg"],
};
</script>

<style scoped>
.alert {
  padding: 20px;
  background-color: #f44336;
  color: white;
  margin-bottom: 1rem;
  position: absolute;
  top: 0px;
  right: 0;
  opacity: 0;
}

.error-msg {
  opacity: 1;
}

.closebtn {
  margin-left: 15px;
  color: white;
  font-weight: bold;
  float: right;
  font-size: 22px;
  line-height: 20px;
  cursor: pointer;
  transition: 0.3s;
}

.closebtn:hover {
  color: black;
}
</style>
