<template>
  <h1>Hello World</h1>
  <Searchbar />
</template>

<script>
import Searchbar from './components/Searchbar.vue';

export default {
  name: 'App',
  components: {
    Searchbar, 
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

* {
  margin : 0;
  padding : 0;
  box-sizing : border-box;
}

</style>