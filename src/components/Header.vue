<template>
  <header>
    <img src="../assets/spotify-logo.png" alt="" />
    <div class="search">
      <genreFilter :genreArray="genreArray" />
    </div>
  </header>
</template>

<script>
import genreFilter from "./genreFilter.vue";
export default {
  name: "Header",
  components: {
    genreFilter,
  },
  props: {
    genreArray: Array,
  },
};
</script>

<style lang="scss" scoped>
header {
  padding: 10px;
  background-color: rgb(46, 58, 70);
  display: flex;
  justify-content: space-between;
  align-items: center;

  img {
    width: 60px;
  }
}
</style>