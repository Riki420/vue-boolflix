<template>
  <div class="col text-white mt-4">
      <div class="card my-s-height bg-dark text-center text-white pointer">
            <div class="card-body">
                <h3>{{ movie.title }}</h3>
                <ul>
                    <li>Voto: {{ movie.vote_average }}</li>
                    <li>Titolo Originale: {{ movie.original_title }}</li>
                    <li>Lingua Originale: {{ movie.original_language }}</li>
                </ul>
            </div>
      </div>
  </div>
</template>

<script>
export default {
    name: "Moviecard",
    props: ["movie"],

    method:{
        
    }
}
</script>

<style>

</style>