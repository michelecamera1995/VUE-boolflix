<template>
  <div id="header">
    <h1>BOOLFLIX</h1>
    <div id="search-box">
      <input type="text" v-model="query" />
      <button>cerca</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",

  data: {
    return: {
      query: "",
    },
  },

  methods: {},
};
</script>

<style lang="scss" scoped>
#header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1%;
  color: red;
  background-color: grey;
  #search-box {
  }
}
</style>