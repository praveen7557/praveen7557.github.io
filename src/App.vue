<template>
  <div id="app">
    <Home/>
  </div>
</template>

<script>
import Home from "./components/Home.vue";

export default {
  name: "app",
  components: {
    Home
  }
};
</script>

<style>
@import "./assets/global.css";

#app {
  font-family: "Source Sans Pro", sans-serif;
  text-align: left;
  color: #000000;
  font-weight: 300;
  background-repeat: no-repeat;
}
</style>
