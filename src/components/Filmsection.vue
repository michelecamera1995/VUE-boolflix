<template>
  <div div class="card">
    <img src="" alt="" />
    <div>
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
  props: {
    film: Object,
  },
};
</script>

<style lang="scss" scoped>
.card {
  padding: 10px;
  line-height: 20px;
  margin: 2%;
  border: 1px solid black;
  width: 15%;
  font-size: 0.9rem;
  height: 250px;
  background-color: white;
}
</style>