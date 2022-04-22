<template>
  <div div class="card" @mouseover="isHovered = true" @mouseleave="isHovered = false">
    <div>
      <img :src="getImgUrl(film)" alt="" v-show="!isHovered" />
      <div v-show="isHovered">
        <h3 class="pad">{{ film.title }}</h3>
        <h3 class="pad">{{ film.original_title }}</h3>
        <img class="flag pad" :src="getFlag(film)" alt="">
        <p class="pad" v-if="this.imgFlag">{{ film.original_language }}</p>
        <h3 class="pad">{{ film.vote_average }}</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {

  name: "Filmsection",

  data() {
    return {
      isHovered : false,
      imgFlag: false,
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
      const urlFlag = "https://www.kidlink.org/icons/f0-" + this.film.original_language + ".gif";
      if(this.film.original_language === 'en'){
        return this.imgFlag=true;
      }
        return urlFlag
    },   
  },
  
};
</script>

<style lang="scss" scoped>
.card {
  img {
    width: 100%;
    height: 100%;
  }
   .flag{
    width: 25px;
  }
  text-align: center;
  padding: 10px;
  line-height: 20px;
  margin: 2%;
  width: 20%;
  font-size: 0.9rem;
  color: white;
  height: 312px;
}
.pad{
  padding-top: 10%;
}
</style>