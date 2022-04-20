<template>
  <div id="header">
    <h1>BOOLFLIX</h1>
    <div id="search-box">
      <input type="text" />
      <button>cerca</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
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