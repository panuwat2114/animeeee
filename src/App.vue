<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <anime/>
  </div>
</template>

<script>

import anime from './components/anime.vue'

export default {
  name: 'App',
  components: {
    anime
  }
}
</script>

<style>
#app {
  font-family: 'Courier New', Courier, monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
  background-color: #2c3e50;
  
}
</style>
