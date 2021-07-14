<template>
  <div class="album-element">
    <img :src="poster" alt="" />
    <div class="title">{{ title }}</div>
    <div class="info">{{ author }}</div>
    <div class="info">{{ year }}</div>
  </div>
</template>

<script>
export default {
  name: "Album",
  props: {
    poster: String,
    title: String,
    author: String,
    year: String,
  },
};
</script>

<style lang="scss" scoped>
.album-element {
  width: calc(100% / 5);
}
</style>