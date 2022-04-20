<template>
  <div>
    <h2>Series</h2>
    <Seriessection
      v-for="series in seriesList"
      :key="series.id"
      :series="series"
    />
    <h2>Film</h2>
    <Filmsection v-for="film in filmList" :key="film.id" :film="film" />
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
</style>