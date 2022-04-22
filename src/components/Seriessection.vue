<template>
  <div div class="card">
    <div>
      <img :src="getImgUrl(series)" alt="" />
      <h3>{{ series.name }}</h3>
      <h3>{{ series.original_name }}</h3>
      <img class="flag" :src="getFlag(film)" alt="">
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
    getFlag() {
      console.log(this.getFlag)
      const urlFlag = "https://www.kidlink.org/icons/f0-" + this.film.original_language + ".gif";
      return urlFlag;
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
   .flag{
    width: 25px;
  }
  text-align: center;
  padding: 10px;
  line-height: 20px;
  margin: 2%;
  border: 1px solid red;
  width: 20%;
  font-size: 0.9rem;
  color: white;
  height: 350px;
  background-color: black;
}
</style>