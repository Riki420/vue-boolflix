<template>
  <div id="app">
    <Header @findFilm="getString"/>
    <Main :movies="movies" :series="series"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import axios from 'axios';
export default {
  name: 'App',
  components: {
    Header,
    Main,  

  },
  data(){
    return{
      movies: [],
      series: [],
      baseUri: "https://api.themoviedb.org/3",
      api_key: "c61c8b4a821d0c1fb04b9ed1012bea69",
      query: "",
      };
  },
  methods: {
            getString(userSrc) {
              this.query = userSrc;
              this.getMovies();
              this.getSeries();
            },
            getMovies() {
              axios.get(`${this.baseUri}/search/movie?api_key=${this.api_key}&query=${this.query}`)
                .then((res) => {
                  this.movies = res.data.results;
              });
            },
            getSeries() {
              axios.get(`${this.baseUri}/search/tv?api_key=${this.api_key}&query=${this.query}`)
                .then((res) => {
                  this.series = res.data.results;
                  console.log(this.series);
            });
            }
    }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

  body{
    background-color: #000;
  }
</style>
