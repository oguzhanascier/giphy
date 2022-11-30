<template>
  <div id="app">
    <search-vue></search-vue>
    <previewVue></previewVue>
  </div>
</template>

<script>
import searchVue from "./components/search.vue";
import previewVue from "./Preview.vue";
export default {
  components: {
    searchVue,
    previewVue
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
