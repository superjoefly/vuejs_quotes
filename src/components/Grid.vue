<template>
  <div class="w3-row-padding">
    <h3 class="w3-center">Click on a Quote to Delete It!</h3>

    <!-- Render Quotes -->
    <!-- Loop through quotes and ouput in slot -->
    <app-quote
      v-for="(quote, index) in quotes"
      @click.native="deleteQuote(index)"
      key="quoteId"
      >{{ quote }}
    </app-quote>

  </div>
</template>

<script>
  import Quote from './Quote.vue';
  export default {
    // Accept 'quotes' as prop
    props: ['quotes'],

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
