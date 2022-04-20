<template>
  <div id="app">
    <Header />
    <Main />
    <button @click="searchFunction"></button>
  </div>
</template>

<script>
import Main from "@/components/Main.vue";
import Header from "@/components/Header.vue";
import axios from "axios";

export default {
  name: "App",

  data() {
    return {
      filmList: [],
      seriesList: [],
      query: "verde",
      apiUrl: "https://api.themoviedb.org/3/search/",
      apiKey: "666c9fe2f4201bb1e9afd43e01e7c534",
    };
  },

  components: {
    Header,
    Main,
  },

  methods: {
    loadApi(type) {
      const settings = {
        api_key: this.apiKey,
        query: this.query,
      };
      axios
        .get(this.apiUrl + type, { settings })
        .then(({ response }) => {
          console.log(response);
        })
        .catch((error) => {
          console.log(error);
        });
    },
    searchFunction() {
      this.loadApi("movie");
    },
  },
};
</script>

<style lang="scss">
body {
  width: 1200px;
  margin: 0 auto;
  background-color: black;
}
</style>
