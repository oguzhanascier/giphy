<template>
  <div id="app">
    <p class="loading" v-if="isLoading">Loading...</p>
    <search-vue @searchRequested="handlerSearch"></search-vue>
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
      isLoading: true,
      gifs: [],
    };
  },
  methods: {
    handlerSearch(query) {
      this.gifs = [];
      this.isLoading = true;
      fetch(
        `https://api.giphy.com/v1/gifs/search?api_key=uwOc1BxEe5fIJ99L8FhncwO9otGUw6xg&q=${query}&limit=25&offset=0&rating=g&lang=en`
      )
        .then((res) => {
          return res.json();
        })
        .then((res) => {
          this.gifs = res.data;
          this.isLoading = false;
        });
    },
  },
  created() {
    fetch(
      "https://api.giphy.com/v1/gifs/trending?api_key=uwOc1BxEe5fIJ99L8FhncwO9otGUw6xg&limit=25&rating=g"
    )
      .then((res) => {
        return res.json();
      })
      .then((res) => {
        this.gifs = res.data;
        this.isLoading = false;
      });
  },
};
</script>

<style>
body {
  background: #687c91;
}

.loading {
  position: absolute;
  top: 20%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 68px;
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
