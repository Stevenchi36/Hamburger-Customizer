<template>
  <div class="hamburger">
    <button>
      <span :style="{ backgroundColor: '#' + lineColor, height: lineHeight + 'px', width: lineWidth + 'px', borderRadius: lineRadius + 'px', marginBottom: lineSpacing + 'px' }"></span>
      <span :style="{ backgroundColor: '#' + lineColor, height: lineHeight + 'px', width: lineWidth + 'px', borderRadius: lineRadius + 'px', marginBottom: lineSpacing + 'px' }"></span>
      <span :style="{ backgroundColor: '#' + lineColor, height: lineHeight + 'px', width: lineWidth + 'px', borderRadius: lineRadius + 'px',  }"></span>
    </button>
  </div>

</template>

<script>
export default {
  props: {
    lineHeight: Number,
    lineWidth: Number,
    lineSpacing: Number,
    lineRadius: Number,
    lineColor: String,
  },
  computed: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  button {
    background-color: transparent;
    padding: 0;
    border: none;
  }

  button:hover {
    cursor: pointer;
  }

  span {
    display: block;
    background-color: red;
  }
</style>
