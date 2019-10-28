<template>
<div class="style">
<h3>CSS</h3>
<pre>
<code>.menu-toggle {
  padding: 0.3rem;
  background-color: transparent;
  border: none;
  z-index: 999;
}

.menu-toggle:hover {
  cursor: pointer;
}

.menu-toggle span {
  display: block;
  background-color: {{ lineColor }};
  height: {{ lineHeight }}px;
  width: {{ lineWidth }}px;
  margin-bottom: {{ lineSpacing }}px;
  border-radius: {{ lineRadius }}px;
  position: relative;
  transition:
    top 0.3s 0.3s ease-in-out,
    bottom 0.3s 0.3s ease-in-out,
    transform 0.3s,
    opacity 0s 0.3s ease-in-out;
}

.menu-toggle.open span {
  transition:
    top 0.3s ease-in-out,
    bottom 0.3s ease-in-out,
    transform 0.3s 0.3s,
    opacity 0s 0.3s ease-in-out;
}

.menu-toggle span:first-child {
  top: 0;
}

.menu-toggle span:nth-child(2) {
  opacity: 1;
}

.menu-toggle span:last-child {
  bottom: 0;
  margin-bottom: 0;
}

.menu-toggle.open span:first-child {
  transform: rotate(45deg);
  transform-origin: center;
  top: {{ Number(lineHeight) + Number(lineSpacing) }}px;
}

.menu-toggle.open span:nth-child(2) {
  opacity: 0;
}

.menu-toggle.open span:last-child {
  transform: rotate(-45deg);
  transform-origin: center;
  bottom: {{ Number(lineHeight) + Number(lineSpacing) }}px;
}</code>
</pre>
</div>
</template>

<script>
export default {
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
</style>
