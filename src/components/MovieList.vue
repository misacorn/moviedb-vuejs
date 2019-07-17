<template>
  <ul>
    <li :key="movie" v-for="movie in movies">
      <Movie :movie="movie"/>
    </li>
  </ul>
</template>

<script>
import Movie from "./Movie";

export default {
  name: "MovieList",
  data() {
    return { movies: [] };
  },
  created: function() {
    this.fetchData();
  },
  methods: {
    fetchData: async function() {
      try {
        const res = await fetch(
          "https://api.themoviedb.org/3/discover/movie?sort_by=popularity.desc&api_key=bf2e9e1f41e52b73e962e7a4c7d1e37b"
        );
        const movies = await res.json();
        this.movies = movies.results;
      } catch (e) {
        console.log(e);
      }
    }
  },
  components: { Movie }
};
</script>

<style lang="scss" scoped>
</style>