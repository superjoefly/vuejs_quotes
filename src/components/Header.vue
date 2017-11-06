<template>
  <div class="w3-container w3-center">
    <h1>Quotes App</h1>
    <p>This App primarily demonstrates component communication in Vue.js</p>

    <div class="w3-light-grey w3-round-large progress">
      <div
      class="w3-blue w3-round-large"
      :style="{width:(quoteCount/maxQuotes) * 100 + '%'}"
      >{{ quoteCount }}</div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['quoteCount', 'maxQuotes']
  }
</script>

<style scoped>
  p {
    font-size: 1.2em;
  }
  @media all and (min-width: 800px) {
    .progress {
      width: 50%;
      margin: auto;
    }
  }
</style>
