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

*, *::before, *::after, html, body {
  font-size: 62.5%;
}

*, html, body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

ul {
  list-style-type: none;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: white;
  width: 100%;
  height: 100%;
  overflow: hidden;
}
</style>
