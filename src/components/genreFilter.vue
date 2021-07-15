<template>
  <div class="genreFilter">
    <label>
      GENERE:
      <select class="genre-selector">
        <option
          v-for="(genre, index) in genreArray"
          :key="index"
          :value="genre"
        >
          {{ genre }}
        </option>
      </select>
    </label>
  </div>
</template>

<script>
export default {
  name: "genreFilter",
  props: {
    genreArray: Array,
  },
};
</script>

<style lang="scss" scoped>
</style>