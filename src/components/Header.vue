<template>
  <header class="container-fluid bg-dark">
      <div class="row">
          <div class="col">
              <div class="container">
                  <div class="row text-red py-2">
                      <div class="col mt-2">
                          <h2>Boolflix</h2>
                      </div>
                      <div class="col mt-2">
                            <div class="input-group mb-3">
                                <input 
                                type="text" 
                                class="form-control" 
                                placeholder="Cerca..."  
                                v-model.trim="searchMovie"
                                @keyup.enter="emitSearch">
                                <button 
                                class="btn btn-outline-secondary" 
                                type="button" 
                                id="button-addon2" 
                                @click="emitSearch">
                                    <i class="bi bi-search"></i>
                                </button>
                            </div>
                      </div>
                  </div>
              </div>
          </div>
      </div>
  </header>
</template>

<script>
export default {
    name: "Header",
    data(){
        return{
            searchMovie: ""
        }
    },
    methods: {
        emitSearch(){
            this.$emit('findFilm', this.searchMovie)
        }
    }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import url("https://cdn.jsdelivr.net/npm/bootstrap-icons@1.5.0/font/bootstrap-icons.css");
@import "../assets/scss/style.scss";

    h2{
        color: $danger;
    }

</style>