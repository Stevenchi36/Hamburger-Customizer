<template>
  <div class="container">
    <label for="lineColor">Color</label>
    <input @input="log('updateColor')" type="color" v-model="lineColor" name="lineColor" id="lineColor">
    <label for="lineHeight">Line Height</label>
    <input @input="log('updateHeight')" v-model="lineHeight" type="range" name="lineHeight" id="lineHeight" min="0" max="50">
    <label for="lineWidth">Line Width</label>
    <input @input="log('updateWidth')" v-model="lineWidth" type="range" name="lineWidth" id="lineWidth" min="0" max="400">
    <label for="lineRadius">Line Border Radius</label>
    <input @input="log('updateRadius')" v-model="lineRadius" type="range" name="lineRadius" id="lineRadius" min="0" max="50">
    <label for="lineSpacing">Line Spacing</label>
    <input @input="log('updateSpacing')" v-model="lineSpacing" type="range" name="lineSpacing" id="lineSpacing" min="0" max="50">
  </div>
</template>

<script>
export default {
  data () {
    return {
      lineHeight: 5,
      lineWidth: 35,
      lineSpacing: 7,
      lineRadius: 5,
      lineColor: '#930eda',
    }
  },
  methods: {
    log: function(valueToChange) {
      if (valueToChange == 'updateHeight') {
        this.$emit(valueToChange, this.lineHeight);
      }
      else if (valueToChange == 'updateWidth') {
        this.$emit(valueToChange, this.lineWidth);
      }
      else if (valueToChange == 'updateRadius') {
        this.$emit(valueToChange, this.lineRadius);
      }
      else if (valueToChange == 'updateColor') {
        this.$emit(valueToChange, this.lineColor);
      }
      else {
        this.$emit(valueToChange, this.lineSpacing);
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .container {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
  }

  input[type=color] {
    margin: 0.4rem 0 0.8rem;
  }
  input[type=range] {
    -webkit-appearance: none;
    margin: 0.8rem 0;
    width: 100%;
    background-color: transparent;
  }
  input[type=range]::-moz-range-track {
    width: 100%;
    height: 6px;
    cursor: pointer;
    animate: 0.2s;
    background: #ffffff;
    border-radius: 1.3px;
  }
  input[type=range]::-moz-range-thumb {
    border: none;
    height: 18px;
    width: 12px;
    border-radius: 3px;
    background: #313131;
    cursor: pointer;
  }
  input[type=range]:focus {
    outline: none;
  }
  input[type=range]::-webkit-slider-runnable-track {
    width: 100%;
    height: 6px;
    cursor: pointer;
    animate: 0.2s;
    background: #ffffff;
    border-radius: 1.3px;
  }
  input[type=range]::-webkit-slider-thumb {
    border: none;
    height: 18px;
    width: 12px;
    border-radius: 3px;
    background: #313131;
    cursor: pointer;
    -webkit-appearance: none;
    margin-top: -14px;
  }
  input[type=range]:focus::-webkit-slider-runnable-track {
    background: #cecece;
  }
  input[type=range]::-ms-track {
    width: 100%;
    height: 6px;
    cursor: pointer;
    animate: 0.2s;
    background: transparent;
    border-color: transparent;
    border-width: 16px 0;
    color: transparent;
  }
  input[type=range]::-ms-fill-lower {
    background: #ffffff;
    border-radius: 2.6px;
  }
  input[type=range]::-ms-fill-upper {
    background: #ffffff;
    border-radius: 2.6px;
  }
  input[type=range]::-ms-thumb {
    border: none;
    height: 18px;
    width: 12px;
    border-radius: 3px;
    background: #313131;
    cursor: pointer;
  }
  input[type=range]:focus::-ms-fill-lower {
    background: #cecece;
  }
  input[type=range]:focus::-ms-fill-upper {
    background: #cecece;
  }
</style>
