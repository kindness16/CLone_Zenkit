<template>
  <div class="app">
    <Zenkit msg="Clone Zenkit" />
  </div>
</template>

<script>
import Zenkit from "./components/Zenkit.vue";

export default {
  name: "App",
  components: {
    Zenkit,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #dce1e6;
  margin-top: 60px;
}
body{
  background: #2c3e50;
}
</style>
