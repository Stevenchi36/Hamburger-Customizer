<template>
  <div id="app">
    <h1 class="title">Hamburger Customizer</h1>
    <Hamburger :lineHeight=5 :lineWidth=35 :lineSpacing=7 :lineRadius=5 :lineColor="'c0ff33'" />
    <Style :lineHeight=5 :lineWidth=35 :lineSpacing=7 :lineColor="'c0ff33'" :lineRadius=5 />
  </div>
</template>

<script>
import Hamburger from './components/Hamburger.vue'
import Style from './components/Style.vue'

export default {
  name: 'app',
  components: {
    Hamburger,
    Style,
  }
}
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  color: #120029;
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}
.title {
  text-align: center;
}
</style>
