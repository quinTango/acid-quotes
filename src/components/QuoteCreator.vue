<template lang="pug">
  div.ex-quote-creator
    textarea(autofocus v-model="text" ref="quoteInput")
    button.btn.btn-primary(@click="publishQuote(text)")
      | Add Quote

</template>

<script>
  export default {
    props: ["addQuote"],
    data: function () {
      return {
        text: ""
      }
    },
    methods: {
      publishQuote: function (text) {
        if(text.length > 1) {
          this.text = ""
          this.$refs.quoteInput.focus();
          this.addQuote(text);
        }
      }
    }
  }
</script>

<style>
</style>


<input type='search' ref='search' placeholder='Keyword:'>

<script>
export default{
   mounted(){
       this.$refs.search.focus();
   }
}
</script>