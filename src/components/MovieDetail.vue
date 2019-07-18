<template>
  <div class="movie-wrapper" :style="styles">
    <div class="movie-info">
      <h1>{{movie.original_title}}</h1>
      <h3>Release Date: {{movie.release_date}}</h3>
      <p>{{movie.overview}}</p>
    </div>
  </div>
</template>

<script>
const BACKDROP_PATH = "http://image.tmdb.org/t/p/w1280";

export default {
  data() {
    return { movie: {} };
  },
  created: function() {
    this.fetchData();
  },
  computed: {
    styles() {
      return {
        background: `url(${BACKDROP_PATH}/${this.movie.backdrop_path}) no-repeat`
      };
    }
  },
  methods: {
    fetchData: async function() {
      try {
        const res = await fetch(
          `https://api.themoviedb.org/3/movie/${this.$route.params.id}?api_key=bf2e9e1f41e52b73e962e7a4c7d1e37b`
        );
        const movie = await res.json();
        this.movie = movie;
      } catch (e) {
        console.log(e);
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.movie-wrapper {
  position: relative;
  padding-top: 90vh;
  margin-left: 5vw;
  padding-right: 6vw;
  background-size: cover;
}
.movie-info {
  background: white;
  color: #222;
  padding: 2rem 10%;
}
</style>