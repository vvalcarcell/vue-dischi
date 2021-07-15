<template>
  <div class="container-fluid">
    <div class="search">
      <genreFilter :genreArray="genreArray" @filter="filterAlbums" />
    </div>

    <div class="container">
      <div v-if="albumsArray.length == 0" class="loading flex">
        Caricamento in corso…
      </div>
      <div v-else class="flex">
        <Album
          v-for="(element, index) in filteredAlbums"
          :key="index"
          :poster="element.poster"
          :title="element.title"
          :author="element.author"
          :year="element.year"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Album from "./Album.vue";
import genreFilter from "./genreFilter.vue";
export default {
  name: "Main",
  components: {
    Album,
    genreFilter,
  },
  props: {
    albumsArray: Array,
    genreArray: Array,
    filteredAlbums: Array,
  },
  methods: {
    filterAlbums(filter) {
      if (filter == "All") {
        this.filteredAlbums = this.albumsArray;
      } else {
        this.filteredAlbums = this.albumsArray.filter((album) => {
          return album.genre.includes(filter);
        });
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.container-fluid {
  padding: 50px 0;
  .loading {
    color: white;
    font-size: 60px;
  }
}
</style>