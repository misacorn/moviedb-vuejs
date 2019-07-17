<template>
  <div>
    <img :src="posterImg" :alt="movie.title" />
  </div>
</template>

<script>
const POSTER_PATH = "http://image.tmdb.org/t/p/w154";

export default {
  props: ["movie"],
  name: "Movie",
  computed: {
    posterImg: function() {
      return `${POSTER_PATH}/${this.movie.poster_path}`;
    }
  }
};
</script>

<style lang="scss" scoped>
img {
  box-shadow: 0 0 35px black;
}
</style>