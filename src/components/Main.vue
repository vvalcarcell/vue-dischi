<template>
  <div class="container">
    <Album
      v-for="(element, index) in albumsArray"
      :key="index"
      :poster="element.poster"
      :title="element.title"
      :author="element.author"
      :year="element.year"
    />
  </div>
</template>

<script>
import Album from "./Album.vue";
export default {
  name: "Main",
  components: {
    Album,
  },
  props: {
    albumsArray: Array,
  },
};
</script>

<style lang="scss" scoped>
</style>