<template>
  <div class="search">
    <input type="text"  v-model="query"/>
    {{query}}
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
};
</script>

<style lang="scss" scoped></style>
