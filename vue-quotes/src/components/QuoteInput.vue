<template>
<div id="quote-input">

  <div class="container mx-auto mt-4">
    <div class="h5">Quote Title:<input v-model="quoteTitle" type="text" class="form-control title mt-1"></div>
    <textarea v-model="quoteText" class="form-control"></textarea>
    <button @click='addQuote()' class="btn btn-primary w-25 mt-3 mx-auto">Add Quote</button>
  </div>
  <hr>

</div>
</template>

<script>
import EventBus from './../EventBus.js';

export default {
  data: () => ({
    quoteText: '',
    quoteTitle: '',

  }),
  methods: {
    addQuote() {
      if (this.quoteText && this.quoteTitle != '') {
        EventBus.$emit('newQuote', {
          quoteTitle: this.quoteTitle,
          quoteText: this.quoteText,
        });
        this.quoteText = '';
        this.quoteTitle = '';

      }
    }
  },
}
</script>


<style lang="scss" scoped>
#quote-input {
    .container {
        .form-control {
            height: 150px !important;
            width: 40% !important;
        }
        .title {
            height: 24px !important;
        }
    }
}
</style>
