<template>
  <div div class="card">
    <img src="" alt="" />
    <div>
      <h3>{{ series.name }}</h3>
      <h3>{{ series.original_name }}</h3>
      <h3>{{ series.original_language }}</h3>
      <h3>{{ series.vote_average }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Seriessection",
  props: {
    series: Object,
  },
};
</script>

<style lang="scss" scoped>
.card {
  padding: 10px;
  line-height: 20px;
  margin: 2%;
  border: 1px solid black;
  width: 10%;
  font-size: 0.7rem;
  height: 200px;
}
</style>