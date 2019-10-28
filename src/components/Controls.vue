<template>
  <div class="container">
    <label for="lineHeight">Line Height</label>
    <input @input="log('updateHeight')" v-model="lineHeight" type="range" name="lineHeight" min="0" max="50">
    <label for="lineWidth">Line Width</label>
    <input @input="log('updateWidth')" v-model="lineWidth" type="range" name="lineWidth" id="" min="0" max="400">
    <label for="lineRadius">Line Border Radius</label>
    <input @input="log('updateRadius')" v-model="lineRadius" type="range" name="lineRadius" id="" min="0" max="50">
    <label for="lineSpacing">Line Spacing</label>
    <input @input="log('updateSpacing')" v-model="lineSpacing" type="range" name="lineSpacing" id="" min="0" max="50">
    <label for="lineSpacing">Color</label>
    <input @input="log('updateColor')" type="color" v-model="lineColor" name="lineColor" id="">
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
      lineColor: 'c0ff33',
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
</style>
