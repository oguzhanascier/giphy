<template>
  <div id="app">
    <search-vue></search-vue>
  </div>
</template>

<script>
import searchVue from "./components/search.vue";
export default {
  components: {
    searchVue,
  },
};
</script>

<style>
body{
  background: #687c91;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
