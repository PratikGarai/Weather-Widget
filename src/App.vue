<template>
  <div id="app1" :class='typeof weather.main!="undefined" && weather.main.temp>20?"warm":""'>
    <main>
      <div class="search">
        <input 
          type="text" 
          class="search__input" 
          placeholder="Search... "
          v-model = "query"
          @keypress = "fetchWeather"
        />
      </div>

      <div class="location" v-if='typeof weather.main!="undefined"'>
        <div class="location__inner">
          <div class="location__name">{{weather.name}}, {{weather.sys.country}}</div>
          <div class="location__date">{{ dateBuilder() }}</div>
        </div>
      </div>

      <div class="weather" v-if="typeof weather.main!='undefined'">
        <div class="weather__temp">{{Math.round(weather.main.temp)}}ºc</div>
        <div class="weather__climate">{{weather.weather[0].main}}</div>
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
      api_key : OPENWEATHERMAP_API_KEY, 
      url_base : 'http://api.openweathermap.org/data/2.5',
      query : '',
      weather : {},
    }
  }, 
  methods : {
    fetchWeather(e) {
      if(e.key=="Enter")
        fetch(`${this.url_base}/weather?q=${this.query}&units=metric&APPID=${this.api_key}`)
        .then(res => res.json())
        .then(res => this.setResults(res));
    }, 
    setResults(res) {
      this.weather = res;
    }, 
    dateBuilder () {
      let d = new Date();
      let months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
      let days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
      let day = days[d.getDay()];
      let date = d.getDate();
      let month = months[d.getMonth()];
      let year = d.getFullYear();
      return `${day} ${date} ${month} ${year}`;
    }
  }
}
</script>

<style>
#app1 {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  background-size : cover;
  background-position : bottom;
  transition : 1s;
  background-image : url('./assets/cold.jpg');
}

main {
  min-height : 100vh;
  padding : 25px;
  background-image : linear-gradient(to bottom, rgba(0,0,0,0.25), rgba(0,0,0,0.75));
  transition : 1s;
}

#app1.warm {
  transition : 1s;
  background-image : url('./assets/warm.jpg');
}

* {
  margin : 0;
  padding : 0;
  box-sizing : border-box;
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