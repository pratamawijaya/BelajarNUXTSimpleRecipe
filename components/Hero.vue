<template>
  <article class="hero">
      <div class="hero-img" :style="{backgroundImage: 'url('+ img +')'}"></div>
      <h1>{{ name }}</h1>
  </article>
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
        width: 240px;
        padding: 8px;
        border: 1px solid #ccc;
        box-shadow: 0 2px 2px #aaa;
        margin: 10px;
    }

    .hero-img {
        background-position: center;
        background-size: cover;
        width: 100%;
        height: 140px;
    }
</style>
