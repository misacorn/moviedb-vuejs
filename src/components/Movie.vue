<template>
  <div>
    <img :src="abc" :alt="movie.title" />
  </div>
</template>

<script>
export default {
  props: ["movie"],
  name: "Movie"
};
</script>

<style lang="scss" scoped>
</style>