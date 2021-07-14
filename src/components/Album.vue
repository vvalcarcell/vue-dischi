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
  max-width: calc(100% / 5 - 20px);
  padding: 20px;
  text-align: center;
  background-color: rgb(46, 58, 70);
  margin-right: 25px;
  margin-bottom: 20px;

  &:nth-of-type(5n + 5) {
    margin-right: 0;
  }

  img {
    max-width: 100%;
  }

  .title {
    font-size: 20px;
    font-weight: bold;
    color: white;
    text-transform: uppercase;
    margin: 10px 0;
  }

  .info {
    font-size: 15px;
    color: grey;
  }
}
</style>