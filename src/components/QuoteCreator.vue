<template lang="pug">
  div.ex-quote-creator
    input( v-model="author" ref="quoteInput")
    textarea( v-model="text" ref="quoteInput")
    button.btn.btn-primary(@click="publishQuote()")
      | Add Quote

</template>

<script>
  export default {
    props: ["addQuote"],
    data: function () {
      return {
        text: "",
        author: ""
      }
    },
    methods: {
      publishQuote: function () {
        if(this.text.length > 1) {
          if(this.author.length > 1) {
            this.addQuote({content: this.text, author: this.author });
            this.author = "";
            this.text = "";
          }else {
            // this.$refs.quoteInput.focus();
            this.addQuote({content: this.text});
            this.text = "";
          }
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