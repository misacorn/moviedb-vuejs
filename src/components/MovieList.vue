<template>
  <div>{{movie.original_title}}</div>
</template>

<script>
export default {
  name: "MovieList",
  data() {
    return { movie: {} };
  },
  created: function() {
    this.fetchData();
  },
  methods: {
    fetchData: async function() {
      try {
        const res = await fetch(
          "https://api.themoviedb.org/3/movie/623?api_key=bf2e9e1f41e52b73e962e7a4c7d1e37b"
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
</style>