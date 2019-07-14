<template>
  <div id="app">
    <Header :title="title" />
    <img alt="Vue logo" src="./assets/logo.png" />
    <ul>
      <li :key="index" v-for="(item, index) in cats">{{item}}</li>
      <li :key="person.id" v-for="person in human">{{person.name}}</li>
      <li :key="index" v-for="(value, key, index) in home">{{key}}: {{value}}</li>
    </ul>
    <HelloWorld :key="person.id" v-for="person in human" msg="Welcome to Your Vue.js App" />
    <!-- this is going to render the components twice -->
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
      cats: ["Salsa", "Mona", "Titi"],
      human: [
        {
          name: "Misa",
          id: "jksse"
        },
        { name: "Tien", id: "kjserk" }
      ],
      home: {
        add: "Antti Korpin tie 4C",
        location: "Koskela",
        city: "Helsinki"
      }
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
