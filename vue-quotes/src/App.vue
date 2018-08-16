<template>
<div id="app">
  <Header></Header>
  <QuoteMeter></QuoteMeter>
  <QuoteInput></QuoteInput>
  <QuoteOutput></QuoteOutput>

</div>
</template>

<script>
import Header from './shared/Header.vue';
import QuoteMeter from './components/QuoteMeter.vue';
import QuoteInput from './components/QuoteInput.vue';
import QuoteOutput from './components/QuoteOutput.vue';



export default {
  components: {
    Header,
    QuoteMeter,
    QuoteInput,
    QuoteOutput
  },

  name: 'app',
  data: () => ({

  })
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
#app {
    font-family: Ubuntu;
}
</style>
