<template>
  <div id="app">
    <search-vue></search-vue>
    <previewVue :gifs="gifs"></previewVue>
  </div>
</template>

<script>
import searchVue from "./components/search.vue";
import previewVue from "./Preview.vue";
export default {
  components: {
    searchVue,
    previewVue,
  },
  data() {
    return {
      gifs:[]
    };
  },
  created() {
    fetch(
      "https://api.giphy.com/v1/gifs/trending?api_key=uwOc1BxEe5fIJ99L8FhncwO9otGUw6xg&limit=25&rating=g"
    )
      .then((res) => {
        return res.json();
      })
      .then((res) => {
        this.gifs=res.data;

        console.log(res.data.url)
        
      });
  },
};
</script>

<style>
body {
  background: #687c91;
}

ul li {
  list-style: none;

}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
