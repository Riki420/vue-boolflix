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
            baseUri: "https://api.themoviedb.org/3",
            api_key: "c61c8b4a821d0c1fb04b9ed1012bea69",
            query: "il+signore+degli+anelli",
            
        }
    },
    method: {
        
    },
    created(){
            axios.get(`${this.baseUri}/search/movie?api_key=${this.api_key}&query=${this.query}`).then((res)=> {
            this.movies = res.data.results;
            console.log(this.movies)
            }
    )}
    
        
}
</script>

<style>

</style>