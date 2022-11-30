<template>
  <div class="search">
    <input type="text"  v-model="query"/>
    <button @click="handleSearch">Search</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      query: "",
    };
  },
  methods:{
    handleSearch(){
      this.$emit('searchRequested', this.query)
    }
  }
};
</script>

<style>
.search{
  width: 100vw;
  display: flex;
  justify-content: center;
}
.search input{
  padding: 10px;
}

.search button{
  background: #1e2a36;
  color: white;
  border: none;
  height: 39.7px;
  border-radius: 0 5px 5px 0;
  cursor: pointer;
}
</style>
