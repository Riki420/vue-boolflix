<template>
  <div class="col text-white mt-4">
      <div class="card my-s-height bg-dark text-center text-white pointer">
            <div class="card-body">
                <h3>{{ serie.name }}</h3>
                <ul>
                    <li>Voto: {{ serie.vote_average }}</li>
                    <li>Titolo Originale: {{ serie.original_name }}</li>
                    <li>Lingua Originale: {{ serie.original_language }}</li>
                </ul>
            </div>
      </div>
  </div>
</template>

<script>
export default {
    props: ['serie']
}
</script>

<style>

</style>