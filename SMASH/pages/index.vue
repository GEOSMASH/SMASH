<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">SMASH</h1>
      <p class="subtitle">Coming Soon.</p>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      script: [
        { src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' },
      ],
    }
  },
}
</script>

<style>
.background {
  /* background-image: url('//unpkg.com/three-globe/example/img/night-sky.png'); */
  background-color: #051622;
}
</style>
