<template>
  <div class="container">
    <progress-bar :progressUnit="quotes.length"></progress-bar>
    <quote-creator :addQuote="addQuote"></quote-creator>
    <quote v-for="(quote, i) in quotes" :removeQuote="removeQuote" :index="i"> {{quote}}</quote>
  </div>
</template>

<script>
  import ProgressBar from "./components/ProgressBar.vue"
  import QuoteCreator from "./components/QuoteCreator.vue"
  import Quote from "./components/Quote.vue"

  export default {
    components: {
      "progress-bar": ProgressBar,
      "quote-creator": QuoteCreator,
      "quote": Quote,
    },
    data: function () {
      return { 
        quotes: ["Locooo", "Alright!"],
      }
    },
    methods: {
      addQuote: function (text) {
        this.quotes.push(text);
      },
      removeQuote: function (index, ev) {
        console.log("here");
        this.quotes.splice(index, 1);
      }
    }
  }
</script>

<style>
</style>
