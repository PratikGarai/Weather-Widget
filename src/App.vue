<template>
  <div class="main">
  </div>
</template>

<script>
export default {
  name: 'App',
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
  background-image : url('./assets/cold.jpg');
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