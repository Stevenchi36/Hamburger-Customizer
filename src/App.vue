<template>
  <div id="app">
    <h1 class="title">Custom Menu Toggle</h1>
    <div class="upper-area">
      <Hamburger :lineHeight="height" :lineWidth="width" :lineSpacing="spacing" :lineRadius="radius" :lineColor="color" />
      <Controls class="style" v-on:updateHeight="heightUpdate" v-on:updateWidth="widthUpdate" v-on:updateRadius="radiusUpdate" v-on:updateSpacing="spacingUpdate" v-on:updateColor="colorUpdate" />
    </div>
    <div class="copy-data">
      <HTML />
      <Style :lineHeight="height" :lineWidth="width" :lineSpacing="spacing" :lineColor="color" :lineRadius="radius" />
      <JS />
    </div>
  </div>
</template>

<script>
import Hamburger from './components/Hamburger.vue'
import Controls from './components/Controls.vue'
import Style from './components/Style.vue'
import HTML from './components/HTML.vue'
import JS from './components/JS.vue'

export default {
  name: 'app',
  components: {
    Hamburger,
    Controls,
    Style,
    HTML,
    JS,
  },
  data () {
    return {
      height: "5",
      width: "35",
      spacing: "7",
      radius: "5",
      color: '#930eda',
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
  body {
    background-color: rgb(248, 239, 255);
    background-image: linear-gradient(to bottom right, rgba(111, 0, 255, 0.288), rgba(255, 0, 0, 0.247));
    min-height: 100vh;
    margin: 0;
  }
  #app {
    font-family: Arial, sans-serif;
    color: #120029;
    max-width: 1200px;
    margin: 0 auto;
    padding: 1rem;
  }
  .title {
    text-align: center;
  }
  .style {
    margin-top: 20px;
  }
  .upper-area {
    display: flex;
  }

  .upper-area > *:first-child {
    flex-basis: 60%;
  }

  .upper-area > *:last-child {
    margin-left: 1rem;
    flex-grow: 1;
  }

  @media screen and (max-width: 767px) {
    .upper-area > *:last-child {
    margin-left: 0;
    }
  }

  @media screen and (max-width: 767px) {
    .upper-area {
      flex-direction: column;
    }
  }
  .copy-data {
    display: flex;
  }

  @media screen and (max-width: 1100px) {
    .copy-data {
      flex-direction: column;
    }
  }
  .copy-data > * {
    flex-grow: 0;
    flex-shrink: 1;
    flex-basis: 33%;
  }

  .copy-data > *:last-child,
  .copy-data > *:nth-child(2) {
    margin-left: 1rem;
  }

  @media screen and (max-width: 1100px) {
    .copy-data > *:last-child,
    .copy-data > *:nth-child(2) {
      margin-left: 0;
    }
  }
</style>
