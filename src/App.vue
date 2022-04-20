<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import Main from "@/components/Main.vue";
import Header from "@/components/Header.vue";

export default {
  name: "App",

  data: {
    return: {
      filmList: [],
      seriesList: [],
    },
  },

  components: {
    Header,
    Main,
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
