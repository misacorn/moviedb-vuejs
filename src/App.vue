<template>
  <div id="app" v-if="status === 'Ready'">
    <Header :title="title" />
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
  <div v-else-if="status === 'Loading'">
    <h1>Loading</h1>
  </div>
  <div v-else>
    <h1>Error</h1>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header.vue";

export default {
  name: "app",
  data() {
    return {
      title: "Vue Movie DB",
      status: "Ready"
    };
  },
  components: {
    Header,
    HelloWorld
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
