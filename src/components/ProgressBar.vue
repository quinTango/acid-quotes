<template lang="pug">
  .ex-progressbar
    p Progress Bar
    div.progress 
      div.progress-bar(role="progressbar" aria-valuenow="70" aria-valuemin="0" aria-valuemax="100" :style="getProgress()")
        | {{progressUnit}}/10
</template>

<script>
  export default {
    props: ["progressUnit"],
    data: function () {
      return { 
        quotes: [],
        welcome: "Welcome"
      }
    },
    methods: {
      getProgress: function () {
        let percentage = this.progressUnit * 10;
        return("width: " + percentage + "%");
      }
    }
  }
</script>

<style scoped>
</style>
