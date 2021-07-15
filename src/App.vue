<template>
  <div id="app">
    <Header />
    <Main
      :albumsArray="albumsArray"
      :genreArray="genreArray"
      :filteredAlbums="filteredAlbums"
    />
  </div>
</template>

<script>
import axios from "axios";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data() {
    return {
      albumsArray: [],
      genreArray: [],
      filteredAlbums: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.albumsArray = response.data.response;
        this.filteredAlbums = response.data.response;
        this.getGenresList();
      });
  },
  methods: {
    getGenresList() {
      this.albumsArray.forEach((element) => {
        if (!this.genreArray.includes(element.genre)) {
          this.genreArray.push(element.genre);
        }
      });
    },
  },
};
</script>

<style lang="sass">
@import "./style/App.scss"
</style>


