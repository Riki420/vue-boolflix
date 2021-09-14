<template>
    <main>
        <div class="container">
            <h1 class="text-white" v-if="movies.length != 0">MOVIE</h1>
            <h3 v-else class="text-center text-white mt-4">Cerca un Film o una Serie TV</h3>

            <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5">
                <!--Movies Cards-->
                <Moviecard v-for="movie in movies" :key="movie.id" :movie="movie"/>
            </div>
            <h1 class="text-white" v-if="series.length != 0">SERIE</h1>
            <span v-else></span>
            <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5">
                <!--Series Cards-->
                <Seriescard v-for="serie in series" :key="serie.id" :serie="serie"/>
            </div>
        </div>
    </main>
</template>

<script>
import Moviecard from './Moviecard.vue'
import Seriescard from './Seriescard.vue'
export default {
    name: "Main",
    props: ["movies", "series"],
    components: {
        Moviecard,
        Seriescard
    },
    data(){
        return{
            
            
        }
    },
    method: {
        
    },  
}
</script>

<style>

</style>