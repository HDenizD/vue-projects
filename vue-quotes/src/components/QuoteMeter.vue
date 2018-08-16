<template>
<div id="quote-meter">

  <div class="h4 mt-5 text-center">Quote Meter</div>
  <div class="progress w-75 h-50 mx-auto">
    <div class="progress-bar" role="progressbar" :style="{width: quoteMeterCalc()+'%', height: '30px'}">{{quoteMeterCalc()/quoteMeterCounterMax}}/{{quoteMeterCounterMax}}</div>
  </div>
  <hr>

</div>
</template>

<script>
import EventBus from './../EventBus.js';
export default {
  data: () => ({
    quoteMeterCounter: 0,
    quoteMeterCounterMax: 10,

  }),
  methods: {
    quoteMeterCalc() {
      var counter = this.quoteMeterCounter;
      counter = counter * 10;
      return counter;
    },
    incCounter() {
      if (this.quoteMeterCounter == this.quoteMeterCounterMax) {
        return alert('to many quotes');
      }
      this.quoteMeterCounter++;
    }

  },
  mounted() {
    EventBus.$on('newQuote', this.incCounter);
  }
}
</script>

<style lang="scss" scoped>
#quote-meter {
    .progress {}
}
</style>
