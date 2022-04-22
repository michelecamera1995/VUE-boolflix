<template>
  <div id="header">
    <h1>BOOLFLIX</h1>
    <div id="search-box">
      <input
        type="text"
        v-model="searchedWord"
        placeholder="Ricerca Film o Serie Tv"
        @keyup.enter="search"
      />
      <button @click="search">cerca</button>
    </div>
  </div>
</template>

<script>
export default {

  name: "Header",

  data() {
    return {
      searchedWord: "",
    };
  },

  methods: {
    search() {
      this.$emit("search", this.searchedWord);
    },
  },
  
};
</script>

<style lang="scss" scoped>
#header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1%;
  color: red;
  background-color: black;
  #search-box {
  }
}
</style>