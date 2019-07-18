<template>
  <header>
    <router-link to="/">
      <h1 color="white">{{title}}</h1>
    </router-link>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: {
    title: String
  }
};
</script>

<style lang="scss" scoped>
header {
  background-color: #111;
  padding: 20px;
}
h1 {
  margin: 0;
}
</style>