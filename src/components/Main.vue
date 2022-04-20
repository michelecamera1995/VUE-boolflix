<template>
  <div>
    <div id="series-section">
      <h2>Series</h2>
      <Seriessection
        v-for="series in seriesList"
        :key="series.id"
        :series="series"
      />
    </div>
    <div id="film-section">
      <h2>Film</h2>
      <Filmsection v-for="film in filmList" :key="film.id" :film="film" />
    </div>
  </div>
</template>

<script>
import Filmsection from "@/components/Filmsection.vue";
import Seriessection from "@/components/Seriessection.vue";

export default {
  name: "Main",
  props: {
    seriesList: Array,
    filmList: Array,
  },
  components: {
    Filmsection,
    Seriessection,
  },
};
</script>

<style lang="scss" scoped>
#film-section {
  display: flex;
  width: 100%;
  flex-wrap: wrap;
  h2 {
    width: 100%;
  }
}
#series-section {
  display: flex;
  width: 100%;
  flex-wrap: wrap;
  display: flex;
  height: 100%;
  h2 {
    width: 100%;
  }
}
</style>