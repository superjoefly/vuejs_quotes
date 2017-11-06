<template>
  <div class="w3-border-bottom w3-center">
    <h3>Add a Quote!</h3>

    <p class="w3-text-red">{{message}}</p>

    <!-- Use v-model to bind the data property to the textarea field -->
      <textarea class="w3-pale-yellow w3-round" placeholder="Enter up to 10 Quotes!" style="width: 100%" rows="3" v-model="newQuote" @keyup.enter="addQuote" @focus="message = ''"/>



    <!-- Add a click listener to execute a method that emits an event and passes the 'newQuote' data -->
    <div class="w3-container">
      <button class="w3-btn w3-blue w3-round w3-margin" @click="addQuote">Add Quote!</button>
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
        if (this.newQuote !== '') {
          this.$emit('quoteAdded', this.newQuote);
          this.newQuote = '';
        } else {
          this.message = 'Enter some text to add a quote!';
        }
      }
    }
  }
</script>

<style>
textarea {
  background: url("http://i.stack.imgur.com/ynxjD.png") repeat-y;
}

@media all and (min-width: 800px) {
  textarea {
    width: 50% !important;
  }
}
</style>
