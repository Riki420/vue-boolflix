<template>
  <div class="col text-white mt-4">
      <div class="card bg-dark text-white pointer p-4">
          <img 
          :src="getImage" 
          :alt="serie.name" 
          class="img-fluid poster">
            <div class="card-body">
                <h3>{{ serie.name }}</h3>
                <ul>
                    <li>Voto: {{ serie.vote_average }}</li>
                    <li>Titolo Originale: {{ serie.original_name }}</li>
                    <li>
                        <img 
                        v-if="flags.includes(serie.original_language)" 
                        :src="getFlag" 
                        alt="movie.original_language" 
                        class="img-fluid w-25">
                        <span v-else>{{ serie.original_language }}</span>
                    </li>
                    <li>
                        <i 
                        v-for="n in 5" 
                        :key="n" 
                        :class="n <= vote ? 'bi-star' : 'bi-star-fill'" 
                        class="bi"></i>
                    </li>
                </ul>
                <p>{{serie.overview}}</p>
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
            imgUrl: 'https://image.tmdb.org/t/p/w500'
        }
    },
    computed:{
        //Recupero l'immagine della lingua
        getFlag(){
            return require(`@/assets/images/${this.serie.original_language}.png`)
        },
        //Recupero l'immagine della serie tv
        getImage(){
            return this.imgUrl + this.serie.poster_path;    
        },
        //Math Ceil sul voto per arrotondare per eccesso, dimezzandolo per 2
        vote(){
            return Math.ceil(this.serie.vote_average / 2);
        }
    }
}
</script>

<style lang="scss" scoped>
.card-body{
    display: none;
    overflow-y: auto;
    ul {
    list-style-type: none;
    }
}
.card:hover .card-body{
    display: block;
    height: 400px;
    
}
.card:hover .poster{
    display: none;
}
</style>