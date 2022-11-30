<template>
  <div>
    <ul>
        <li v-for="gif in gifs" :key="gif"></li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["gifs"],
};
</script>

<style></style>
