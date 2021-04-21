<template>
  <div class="main">
    <main>
      <div class="search">
        <input type="text" class="search__input" placeholder="Search... "/>
      </div>
    </main>
  </div>
</template>

<script>
import {OPENWEATHERMAP_API_KEY} from "./secrets.js";

export default {
  name: 'App',
  data() {
    return {
      api_key : OPENWEATHERMAP_API_KEY
    }
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
  background-image : url('./assets/cold.jpg');
  background-size : cover;
  background-position : bottom;
  transition : 0.4s;
}

.main {
  min-height : 100vh;
  padding : 25px;

  background-image : linear-gradient(to bottom, rgba(0,0,0,0.25), rgba(0,0,0,0.75));
}

.search {
  width : 100%;
  margin-bottom : 30px;
}

.search__input {
  display : block;
  width : 100%;
  padding : 15px;
  color : #313131;
  font-size : 20px;
  appearance : none;
  border : none;
  outline : none;
  background : none;

  background-color : rgba(255, 255, 255, 0.5);
  border-radius : 0px 16px 0px 16px;
  transition : 0.4s;
  box-shadow : 0px 0px 8px rgba(0,0,0,0.25);
}

.search__input:focus {
  box-shadow : 0px 0px 16px rgba(0,0,0,0.25);
  border-radius : 16px 0px 16px 0px;
  background-color : rgba(255, 255, 255, 0.75);
}

</style>