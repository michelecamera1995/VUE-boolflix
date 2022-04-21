<template>
  <div div class="card">
    <div>
      <img :src="getImgUrl(series)" alt="" />
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
  methods: {
    getImgUrl() {
      const url = "https://image.tmdb.org/t/p/w200" + this.series.poster_path;
      return url;
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  img {
    width: 70%;
    height: 70%;
  }
  text-align: center;
  padding: 10px;
  line-height: 20px;
  margin: 2%;
  border: 1px solid black;
  width: 25%;
  font-size: 0.9rem;
  color: white;
  height: 400px;
  background-color: black;
}
</style>