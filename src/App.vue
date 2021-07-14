<template>
  <div id="app">
    <Header />
    <Main :albumsArray="albumsArray" />
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
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.albumsArray = response.data.response;
      });
  },
};
</script>

<style lang="sass" scoped>
</style>

