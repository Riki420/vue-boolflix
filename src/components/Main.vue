<template>
    <main>
        <div class="container">
            <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5">
                <!--Movie Cards-->
                <Moviecard v-for="movie in movies" :key="movie.id" :movie="movie"/>
            </div>
        </div>
    </main>
</template>

<script>
import Moviecard from './Moviecard.vue'
export default {
    name: "Main",
    props: ["movies"],
    components: {
        Moviecard,
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