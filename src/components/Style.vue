<template>
<div class="style">
<h3>CSS</h3>
<pre>
<code>.hamburger .span {
  background-color: {{ lineColor }};
  height: {{ lineHeight }}px;
  width: {{ lineWidth }}px;
  margin-bottom: {{ lineSpacing }}px;
  border-radius: {{ lineRadius }}px;
}

.hamburger .span:last-child {
  margin-bottom: 0;
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
