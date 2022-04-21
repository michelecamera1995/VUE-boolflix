<template>
  <div id="app">
    <Header @search="loadApi" />
    <Main :filmList="filmList" :seriesList="seriesList" />
  </div>
</template>

<script>
import Main from "@/components/Main.vue";
import Header from "@/components/Header.vue";
import axios from "axios";

export default {
  name: "App",

  components: {
    Header,
    Main,
  },

  data() {
    return {
      filmList: [],
      seriesList: [],
      searching: false,
      apiUrl: "https://api.themoviedb.org/3/search/",
      apiKey: "7b0221641cd6cccd42ea4445b3c56e3d",
    };
  },

  methods: {
    loadApi(searchedWord) {
      //console.log(searchedWord);
      this.searching = true;
      const params = {
        api_key: this.apiKey,
        query: searchedWord,
        language: "it-IT",
      };
      if (searchedWord > 0 && !this.searching) {
        axios
          .get(this.apiUrl + "movie", { params })
          .then((response) => {
            this.filmList = response.data.results;
            this.searching = false;
            console.log(this.filmList);
          })
          .catch((error) => {
            console.log(error);
          });
        axios
          .get(this.apiUrl + "tv", { params })
          .then((response) => {
            this.seriesList = response.data.results;
            this.searching = false;
            console.log(this.seriesList);
          })
          .catch((error) => {
            console.log(error);
          });
      }
    },
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  width: 1200px;
  margin: 0 auto;
  background-color: grey;
}
</style>
