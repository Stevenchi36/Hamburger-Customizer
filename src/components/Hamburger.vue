<template>
  <div class="container">
    <button class="make-fixed" @click='isFixed = !isFixed'>Toggle button position</button>
    <button @click="isOpen = !isOpen" :class="[{open: isOpen} , {fixed: isFixed}]" class="menu-toggle">
      <span :style="[!isOpen ? { backgroundColor: lineColor, height: lineHeight + 'px', width: lineWidth + 'px', borderRadius: lineRadius + 'px', marginBottom: lineSpacing + 'px' } : {backgroundColor: lineColor, height: lineHeight + 'px', width: lineWidth + 'px', borderRadius: lineRadius + 'px', marginBottom: lineSpacing + 'px', top: Number(lineHeight) + Number(lineSpacing) + 'px'}]"></span>
      <span :style="{ backgroundColor: lineColor, height: lineHeight + 'px', width: lineWidth + 'px', borderRadius: lineRadius + 'px', marginBottom: lineSpacing + 'px' }"></span>
      <span :style="[!isOpen ? { backgroundColor: lineColor, height: lineHeight + 'px', width: lineWidth + 'px', borderRadius: lineRadius + 'px'} : {backgroundColor: lineColor, height: lineHeight + 'px', width: lineWidth + 'px', borderRadius: lineRadius + 'px', bottom: Number(lineHeight) + Number(lineSpacing) + 'px'}]"></span>
    </button>
    <p>Click on the menu toggle to view the transition.</p>
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
    lineHeight: String,
    lineWidth: String,
    lineSpacing: String,
    lineRadius: String,
    lineColor: String,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 2rem 0;
    border: 1px solid hsla(0, 0%, 83%, 25%);
    min-height: 200px;
    max-height: 400px;
    position: relative;
  }
  p {
    position: absolute;
    bottom: 0.3rem;
    left: 0.3rem;
    margin-bottom: 0;
    color: #535353;
    font-size: 0.8rem;
  }

  .make-fixed {
    position: absolute;
    top: 1rem;
    left: 1rem;
    background-color: white;
    border: 1px solid black;
    padding: 0.5rem;
    font-size: 1rem;
  }

  .menu-toggle {
    background-color: transparent;
    padding: 0.5rem;
    border: none;
    z-index: 999;
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
    position: relative;
    transition: top 0.3s 0.3s ease-in-out, bottom 0.3s 0.3s ease-in-out, transform 0.3s, opacity 0s 0.3s ease-in-out;
  }

  .open span {
    transition: top 0.3s ease-in-out, bottom 0.3s ease-in-out, transform 0.3s 0.3s ease-in-out, opacity 0s 0.3s ease-in-out;
  }

  span:first-child {
    top: 0;
  }

  span:nth-child(2) {
    opacity: 1;
  }

  span:last-child {
    bottom: 0;
  }

  .open span:first-child {
    transform: rotate(45deg);
    transform-origin: center;
  }

  .open span:nth-child(2) {
    opacity: 0;
  }

  .open span:last-child {
    transform: rotate(-45deg);
    transform-origin: center;
  }
</style>
