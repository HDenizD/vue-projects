<template>
<div id="quote-output" class="container mx-auto w-75">

  <div class="card-group">
    <div v-for="(quote, i) in quotes" :key="i" class="card text-white bg-primary mb-3" style="max-width: 18rem;">
      <div class="card-header">{{quote.title}}</div>
      <div class="card-body">
        <h5 class="card-title">Primary card title</h5>
        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
      </div>
    </div>
    <div class="mx-2"></div>

  </div>

</div>
</template>

<script>
import EventBus from './../EventBus.js';

export default {
  data: () => ({
    quotes: [{
      title: '',
      text: '',
    }],


  }),
  mounted() {
    EventBus.$on('newQuote', ({
      quoteTitle,
      quoteText,
    }) => {
      console.log(quoteTitle);
      console.log(quoteText);
      this.quotes.push('test');

    })
  }
}
</script>

<style lang="scss" scoped>
#quote-output {
  .card-group{
    .card{
      border-radius: 0 !important;
    }
  }
}
</style>
