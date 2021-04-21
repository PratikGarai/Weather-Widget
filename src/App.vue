<template>
  <div class="main">
    <main>

      <div class="search">
        <input type="text" class="search__input" placeholder="Search... "/>
      </div>

      <div class="location">
        <div class="location__inner">
          <div class="location__name">Kolkata</div>
          <div class="location__date">Sunday 21 April 2021</div>
        </div>
      </div>

      <div class="weather">
        <div class="weather__temp">25ºC</div>
        <div class="weather__climate">Rain</div>
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

.location__name {
  color : #fff;
  font-size : 32px;
  font-weight : 500;
  text-align : center;
  text-shadow : 1px 3px rgba(0,0,0,0.25);
}

.location__date {
  color : #fff;
  font-size : 20px;
  font-weight : 300;
  font-style : italic;
  text-align : center;
}

.weather {
  text-align : center;
}

.weather__temp{
  display : inline-block;
  padding : 10px 25px;
  color : #fff;
  font-size : 102px;
  font-weight : 900;

  text-shadow : 3px 6px rgba(0,0,0,0.25);
  background-color : rgba(255,255,255,0.25);
  border-radius : 16px;
  margin : 30px 0;

  box-shadow : 3px 6px rgba(0,0,0,0.25);
}

.weather__climate{
  color : #fff;
  font-size : 48px;
  font-weight : 700;
  font-style : italic;
  text-shadow : 3px 6px rgba(0,0,0,0.25);
}

</style>