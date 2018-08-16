<template>
<div id="app">
  <Header></Header>
  <Todo class="pt-3"></Todo>
</div>
</template>

<script>
import Header from './shared/Header.vue';
import Todo from './components/Todo.vue';
export default {
  components:{
    Header,
    Todo,
  },
  name: 'app',
  data() {
    return {

    }
  }
}
</script>

<style lang="scss">
@import "~bootstrap/dist/css/bootstrap.css";
#app {
  font-family: Ubuntu;
}

</style>
