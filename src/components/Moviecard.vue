<template>
  <div class="col text-white mt-4">
      <div class="card my-s-height bg-dark text-center text-white pointer">
            <div class="card-body">
                <figure>
                    <img :src="('https://image.tmdb.org/t/p/w342'+[movie.poster_path])" alt="movie.title" class="img-fluid pointer">
                </figure>
            </div>
      </div>
  </div>
</template>

<script>
export default {
    name: "Moviecard",
    props: ['movie'],

    method:{
        
    }
}
</script>

<style>

</style>