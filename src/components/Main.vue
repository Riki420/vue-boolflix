<template>
    <main>
        <div class="container">
            <h1 class="text-white">MOVIE</h1>
            <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5">
                <!--Movies Cards-->
                <Moviecard v-for="movie in movies" :key="movie.id" :movie="movie"/>
            </div>
            <h1 class="text-white">SERIE</h1>
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