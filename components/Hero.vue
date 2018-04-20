<template>
  <hero class="hero">
      <div class="hero-img" :style="{backgroundImage: 'url('+ img +')'}"></div>
      <h1>hero name</h1>
  </hero>
</template>

<script>
export default {
  props: [
      "id",
      "name",
      "img"
  ]
}
</script>

<style>
    .hero {
        box-sizing: border-box;
        width: 200px;
        padding: 8px;
        border: 1px solid #ccc;
        box-shadow: 0 2px 2px #aaa;
        margin: 10px;
    }

    .thumbnail {
        background-position: center;
        background-size: cover;
        width: 100%;
        height: 200px;
    }
</style>
