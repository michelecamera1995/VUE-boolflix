<template>
  <div div class="card">
    <div>
      <img :src="getImgUrl(film)" alt="" />
      <h3>{{ film.title }}</h3>
      <h3>{{ film.original_title }}</h3>
      <h3>{{ film.original_language }}</h3>
      <h3>{{ film.vote_average }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Filmsection",
  data() {
    return {
      imgUrl: "",
    };
  },
  props: {
    film: Object,
  },
  methods: {
    getImgUrl() {
      const url = "https://image.tmdb.org/t/p/w200" + this.film.poster_path;
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