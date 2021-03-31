<template>
  <div class="main">
    <Searchbar />
  </div>
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

#app {
  background-image : url('./assets/hot.jpg');
  background-size : cover;
  background-position : bottom;
  transition : 0.4s;
}

.main {
  min-height : 100vh;
  padding : 25px;

  background-image : linear-gradient(to bottom, rgba(0,0,0,0.25), rgba(0,0,0,0.50));
}

</style>