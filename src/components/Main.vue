<template>
  <div>
    <Seriessection
      v-for="series in seriesList"
      :key="series.id"
      :series="series"
    />
    <Filmsection v-for="film in filmList" :key="film.id" :film="film" />
    <button @click="consolelog">consolelog</button>
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
  methods: {
    consolelog() {
      console.log(this.seriesList);
      console.log(this.filmList);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>