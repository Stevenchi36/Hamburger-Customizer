<template>
<div class="style">
<h3>JavaScript</h3>
<pre>
<code>const menuToggle = document.querySelector('.menu-toggle');

menuToggle.addEventListener('click', function() {
  menuToggle.classList.toggle('open');
  // Add things here to toggle your actual menu
});</code>
</pre>
</div>
</template>

<script>
export default {
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  code {
    display: block;
    max-width: 100%;
    max-height: 400px;
    height: 400px;
    overflow: auto;
    padding: 0.2rem;
    outline: 1px solid hsla(0, 0%, 83%, 25%);
    background-color: rgb(243, 243, 243);
  }

  @media screen and (max-width: 1100px) {
    code {
      height: auto;
    }
  }
</style>
