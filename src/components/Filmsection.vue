<template>
  <div id="film-section">
    <img src="" alt="" />
    <div class="card">{{ film.title }}</div>
  </div>
</template>

<script>
export default {
  name: "Filmsection",
  props: {
    film: Object,
  },
};
</script>

<style lang="scss" scoped>
#film-section {
  width: 100%;
  display: flex;
  height: 100%;
  .card {
    width: 10%;
    height: 50px;
  }
}
</style>