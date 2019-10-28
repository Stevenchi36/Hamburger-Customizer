<template>
  <div id="app">
    <h1 class="title">Hamburger Customizer</h1>
    <Hamburger :lineHeight="height" :lineWidth="width" :lineSpacing="spacing" :lineRadius="radius" :lineColor="color" />
    <Controls class="style" v-on:updateHeight="heightUpdate" v-on:updateWidth="widthUpdate" v-on:updateRadius="radiusUpdate" v-on:updateSpacing="spacingUpdate" v-on:updateColor="colorUpdate" />
    <Style :lineHeight="height" :lineWidth="width" :lineSpacing="spacing" :lineColor="color" :lineRadius="radius" />
  </div>
</template>

<script>
import Hamburger from './components/Hamburger.vue'
import Controls from './components/Controls.vue'
import Style from './components/Style.vue'

export default {
  name: 'app',
  components: {
    Hamburger,
    Controls,
    Style,
  },
  data () {
    return {
      height: 5,
      width: 35,
      spacing: 7,
      radius: 5,
      color: 'c0ff33',
    }
  },
  methods: {
    heightUpdate: function(value) {
      this.height = value;
    },
    widthUpdate: function(value) {
      this.width = value;
    },
    radiusUpdate: function(value) {
      this.radius = value;
    },
    spacingUpdate: function(value) {
      this.spacing = value;
    },
    colorUpdate: function(value) {
      this.color = value;
    },
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
.style {
  margin-top: 20px;
}
</style>
