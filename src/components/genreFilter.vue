<template>
  <div class="genreFilter">
    <label>
      GENERE:
      <select
        class="genre-selector"
        v-model="chosenGenre"
        @change="$emit('filter', chosenGenre)"
      >
        <option value="">All</option>
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
  data() {
    return {
      chosenGenre: "",
    };
  },
};
</script>

<style lang="scss" scoped>
</style>