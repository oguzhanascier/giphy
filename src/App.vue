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
  created(){
    fetch('https://api.giphy.com/v1/gifs/trending?api_key=uwOc1BxEe5fIJ99L8FhncwO9otGUw6xg&limit=25&rating=g')
    .then((res)=> {
      return res.json()})
      .then((res) => {console.log(res)})
  }
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
