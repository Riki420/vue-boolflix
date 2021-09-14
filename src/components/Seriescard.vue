<template>
  <div class="col text-white mt-4">
      <div class="card my-s-height bg-dark text-center text-white pointer">
            <div class="card-body">
                <h3>{{ serie.name }}</h3>
                <ul>
                    <li>Voto: {{ serie.vote_average }}</li>
                    <li>Titolo Originale: {{ serie.original_name }}</li>
                    <li>
                        <img v-if="flags.includes(serie.original_language)" :src="getFlag" alt="movie.original_language" class="img-fluid w-25">
                        <span v-else>{{ serie.original_language }}</span>
                    </li>
                </ul>
            </div>
      </div>
  </div>
</template>

<script>
export default {
    props: ['serie'],
    data(){
        return{
            flags: ["en", "it"],
            imgUri: 'https://image.tmdb.org/t/p/w500'
        }
    },
    computed:{
        getFlag(){
            return require(`@/assets/images/${this.serie.original_language}.png`)
        }
    }
}
</script>

<style>

</style>