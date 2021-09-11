<template>
    <main>
        <div class="container">
            <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5">
                <!--Movie Cards-->
                <Moviecard :movies="movies" v-for="movie in movies" :key="movie.id" :movie="movie"/>
            </div>
        </div>
    </main>
</template>

<script>
import Moviecard from './Moviecard.vue'
import axios from 'axios';
export default {
    name: "Main",
    components: {
        Moviecard,
    },
    data(){
        return{
            movies: [],
        }
    },
    created(){
    axios.get('https://api.themoviedb.org/3/search/movie?api_key=c61c8b4a821d0c1fb04b9ed1012bea69&query=ritorno+al+futuro').then((res)=> {
        this.movies = res.data.results;
        }
    )}
        
}
</script>

<style>

</style>