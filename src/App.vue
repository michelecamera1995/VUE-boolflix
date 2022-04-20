<template>
  <div id="app">
    <Header @digit="doSearch" />
    <Main :filmList="filmList" :seriesList="seriesList" />
    <button @click="searchFunction">
      INSERISCI UNA PAROLA IN CERCA E CLICCA
    </button>
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
      query: "",
      searching: false,
      apiUrl: "https://api.themoviedb.org/3/search/",
      apiKey: "7b0221641cd6cccd42ea4445b3c56e3d",
    };
  },

  computed: {
    filteredFilms() {
      const textToSearch = this.query.toLowerCase().trim();
      if (!textToSearch) {
        return this.filmList;
      }
      return filmList.filter((film) => {
        return film.name.toLowerCase().includes(textToSearch);
      });
    },
  },

  methods: {
    doSearch(text) {
      this.query = text;
    },
    searchFunction() {
      if (this.query.length > 0 && !this.searching) {
        this.loadApi("tv").then((response) => {
          this.seriesList = response.data.results;
          //console.log(this.seriesList);
        });
        this.loadApi("movie").then((response) => {
          this.filmList = response.data.results;
          //console.log(this.filmList);
        });
      }
    },

    loadApi(type) {
      this.searching = true;
      const params = {
        api_key: this.apiKey,
        query: this.query,
        language: "it-IT",
      };
      return axios.get(this.apiUrl + type, { params }).catch((error) => {
        console.log(error);
      });
    },

    queryTvSeries() {
      this.loadApi("tv");
    },

    queryMovies() {
      this.loadApi("movie");
    },
  },
};
</script>

<style lang="scss">
body {
  width: 1200px;
  margin: 0 auto;
  background-color: grey;
}
</style>
