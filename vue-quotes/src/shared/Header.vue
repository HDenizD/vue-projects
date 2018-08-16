<template lang="html">

  <div id="header">
    <div class="jumbotron jumbotron-fluid text-center border-bottom border-top border-dark">
      <div class="container">
        <h1 class="display-4">{{pageTitle1}}<span class="dash">{{pageTitle2}}</span>{{pageTitle3}}<img src="src/assets/logo.png" alt=""></h1>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  data() {
    return {
      pageTitle1: 'Vue',
      pageTitle2: '-',
      pageTitle3: 'Quotes',
    };
  }
}
</script>

<style scoped lang="scss">
#header {
    .border-dark {
        border-color: #000000;
    }
    .jumbotron {
        padding: 15px !important;
        margin-bottom: 0 !important;
        .container {
            h1 {
                .dash {
                    color: #000000;
                }
                color: #007bff;
                img {
                    height: 50px;
                    width: auto;
                    margin-left: 1%;
                }
            }
        }
    }
}
</style>
