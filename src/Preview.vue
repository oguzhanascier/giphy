<template>
  <div class="container">
    <ul>
        <li v-for="(gif, index) in gifs" :key="index">
            <img :src="gif.images.fixed_height.url" alt="" />
        </li>
        
    </ul>
  </div>
</template>

<script>
export default {
  props: ["gifs"],
};
</script>

<style>
.container{
    width: 100vw;
    display: flex;
}

ul{
display: flex;
justify-content: center;
gap: 15px;
flex-wrap: wrap;
}



img{
    width: 300px;
    height: 300px;
}
</style>
