<template>
  <div div class="card">
    <div>
      <img :src="getImgUrl(film)" alt="" />
      <h3>{{ film.title }}</h3>
      <h3>{{ film.original_title }}</h3>
      <img class="flag" :src="getFlag(film)" alt="">
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
  font-size: 0.8rem;
  color: white;
  height: 350px;
  background-color: black;
}
</style>