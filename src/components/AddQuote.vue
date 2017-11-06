<template>
  <div class="w3-border-bottom w3-center">
    <h3>Add a Quote!</h3>

    <p class="w3-text-red">{{message}}</p>

      <input class="w3-input" placeholder="Enter up to 10 Quotes!" style="width: 100%" v-model="newQuote" @keyup.enter="addQuote($event.target.value)" autofocus @focus="message = ''"/>



    <!-- Add a click listener to execute a method that emits an event and passes the 'newQuote' data -->
    <div class="w3-container">
      <button class="w3-btn w3-blue w3-round w3-margin" @click="addQuote($event)">Add Quote!</button>
    </div>


  </div>
</template>

<script>
  export default {
    data() {
      return {
        newQuote: '',
        message: ''
      }
    },

    methods: {
      addQuote() {
        if(this.newQuote == '') {
          this.message = 'Enter some text to add a quote!';
        } else {

          this.$emit('quoteAdded', this.newQuote);
          this.newQuote = '';
          this.message = '';
        }
      }
    }
  }
</script>

<style>

@media all and (min-width: 800px) {
  input {
    width: 50% !important;
    margin: auto;
  }
}
</style>
