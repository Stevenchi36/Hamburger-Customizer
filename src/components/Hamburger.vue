<template>
  <div class="container">
    <button class="make-fixed" @click='isFixed = !isFixed'>Toggle button Position</button>
    <button @click="isOpen = !isOpen" :class="[{open: isOpen} , {fixed: isFixed}]" class="menu-toggle">
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
      isFixed: false,
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
    position: relative;
  }

  .make-fixed {
    position: absolute;
    top: 1rem;
    left: 1rem;
  }

  .menu-toggle {
    background-color: transparent;
    padding: 0;
    border: none;
  }

  .menu-toggle:hover {
    cursor: pointer;
  }

  .menu-toggle.fixed  {
    position: fixed;
    top: 1rem;
    right: 1rem;
  }

  span {
    display: block;
  }
</style>
