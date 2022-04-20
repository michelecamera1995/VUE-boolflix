<template>
  <div id="series-section">
    <div class="card">{{ series.name }}</div>
  </div>
</template>

<script>
export default {
  name: "Seriessection",
  props: {
    series: Object,
  },
};
</script>

<style lang="scss" scoped>
#series-section {
  width: 100%;
  display: flex;
  height: 100%;
  .card {
    width: 10%;
    height: 50px;
  }
}
</style>