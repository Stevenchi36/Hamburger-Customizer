<template>
  <div id="app">
    <h1>Hamburger Customizer</h1>
    <Hamburger />
  </div>
</template>

<script>
import Hamburger from './components/Hamburger.vue'

export default {
  name: 'app',
  components: {
    Hamburger
  }
}
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #120029;
  margin-top: 60px;
}
</style>
