<template>
  <div class="w3-row-padding">
    <h3 class="w3-center">Click on a Quote to Delete It!</h3>

    <!-- Render Quotes -->
    <!-- Loop through quotes and ouput in slot -->

    <app-quote
      v-for="(quote, index) in quotes"
      @click.native="deleteQuote(index)"
      key="quoteId"
      >
      <div class="w3-panel w3-cyan w3-round">
        {{ quote }}
      </div>
    </app-quote>

  </div>
</template>

<script>
  import Quote from './Quote.vue';
  export default {
    // Accept 'quotes' as prop
    props: ['quotes'],

    data() {
      return {
        showCloseButton: false
      }
    },

    methods: {
      deleteQuote(index) {
        this.$emit('quoteDeleted', index);
      }
    },

    components: {
      appQuote: Quote
    }
  }
</script>


<style scoped>
  .w3-panel {
      font-family: 'Love Ya Like A Sister', cursive;
      font-size: 24px;
      color: white !important;
      word-wrap: break-word;
      position: relative;
  }

  .w3-panel:after {
    content: "";
    position: absolute;
    bottom: -20px;
    left: 50px;
    border-width: 20px 20px 0 0;
    border-style: solid;
    border-color: #00bcd4 transparent;
    display: block;
    width: 0;
  }

  .w3-panel:hover {
    cursor: pointer;
    border-bottom: 1px solid red;
  }

  .close-button {
    position: absolute;
    right: 5px;
    color: red;
  }
</style>
