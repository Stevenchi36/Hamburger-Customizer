<template>
  <div class="container">
    <button @click="isOpen = !isOpen" :class="{open: isOpen}">
      <span :style="{ backgroundColor: lineColor, height: lineHeight + 'px', width: lineWidth + 'px', borderRadius: lineRadius + 'px', marginBottom: lineSpacing + 'px' }"></span>
      <span :style="{ backgroundColor: lineColor, height: lineHeight + 'px', width: lineWidth + 'px', borderRadius: lineRadius + 'px', marginBottom: lineSpacing + 'px' }"></span>
      <span :style="{ backgroundColor: lineColor, height: lineHeight + 'px', width: lineWidth + 'px', borderRadius: lineRadius + 'px',  }"></span>
    </button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isOpen: false,
    }
  },
  props: {
    lineHeight: Number,
    lineWidth: Number,
    lineSpacing: Number,
    lineRadius: Number,
    lineColor: String,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .container {
    display: flex;
    justify-content: center;
    padding: 2rem 0;
    border: 1px solid hsl(0, 0%, 83%);
    min-height: 200px;
    max-height: 400px;
  }

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
  }
</style>
