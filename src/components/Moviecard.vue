<template>
<div>
    <div class="col text-white mt-4">
      <div class="card my-s-height bg-dark text-center text-white pointer p-4">
          <img 
          :src="getImage" 
          :alt="movie.title" 
          class="img-fluid">
            <div class="card-body">
                <h3>{{ movie.title }}</h3>
                <ul>
                    <li>Voto: {{ movie.vote_average }}</li>
                    <li>Titolo Originale: {{ movie.original_title }}</li>
                    <li>
                        <img 
                        v-if="flags.includes(movie.original_language)" 
                        :src="getFlag" 
                        alt="movie.original_language" 
                        class="img-fluid w-25">
                        <span v-else>{{ movie.original_language }}</span>
                    </li>
                    <li>
                        <i 
                        v-for="n in 5" 
                        :key="n" 
                        :class="n <= vote ? 'bi-star' : 'bi-star-fill'" 
                        class="bi"></i>
                    </li>
                </ul>
            </div>
      </div>
  </div>
</div>
  
</template>

<script>

export default {
    name: "Moviecard",
    props: ["movie"],
    data(){
        return{
            flags: ["en", "it"],
            imgUrl: 'https://image.tmdb.org/t/p/w500'
        }
    },
    computed:{
        //Recupero l'immagine della lingua
        getFlag(){
            return require(`@/assets/images/${this.movie.original_language}.png`)
        },
        //Recupero l'immagine del film
        getImage(){
            return this.imgUrl + this.movie.poster_path;    
        },
        //Math Ceil sul voto per arrotondare per eccesso, dimezzandolo per 2
        vote(){
            return Math.ceil(this.movie.vote_average / 2);
        }
    }
}
</script>

<style lang="scss" scoped>

.card-body{
    display: none;
    &:hover{
        display: block;
    }
}


</style>