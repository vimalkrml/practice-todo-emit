<template>
  <div id="app">
    <homevue />
  </div>
</template>

<script>
import Homevue from "./components/HomePage.vue";
export default {
  name: "App",
  components: { Homevue },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
