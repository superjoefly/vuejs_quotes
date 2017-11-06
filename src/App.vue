<template>
  <div class="w3-container">

    <!-- Render Header Component -->

    <!-- Bind quoteCount and maxQuotes data to pass as props -->
    <app-header
    :quoteCount="quotes.length"
    :maxQuotes="maxQuotes"
    ></app-header>



    <!-- Render AddQuote Component -->

    <!-- Listen for the custom event 'quoteAdded', and execute a method that passes the 'newQuote' data and pushes to the array -->
    <app-add-quote @quoteAdded ="createQuote"></app-add-quote>



    <!-- Render Grid -->

    <!-- Bind 'quotes' data to component to pass as props -->
    <app-grid
    :quotes="quotes"
    @quoteDeleted="removeQuote"
    ></app-grid>


  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import AddQuote from './components/AddQuote.vue';
  import Grid from './components/Grid.vue';

  export default {
    data() {
      return {
        quotes: [
          'This is a quote!'
        ],
        maxQuotes: 10
      }
    },

    methods: {
      createQuote(newQuote) {
        if (this.quotes.length >= this.maxQuotes) {
          return alert('Please delete some quotes first!');
        }
        this.quotes.push(newQuote);
      },

      removeQuote(index) {
        this.quotes.splice(index, 1);
      }
    },

    components: {
      appHeader: Header,
      appAddQuote: AddQuote,
      appGrid: Grid
    }
  }
</script>
