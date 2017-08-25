<template lang="pug">
  div.ex-quote(@click="removeQuote(index)")
    slot
</template>

<script>
  export default {
    props: ["removeQuote", "index"],
    data: function () {
      return {}
    }
  }
</script>

<style>
</style>
