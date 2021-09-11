<template>
  <header class="container-fluid bg-dark">
      <div class="row">
          <div class="col">
              <div class="container">
                  <div class="row text-red py-4">
                      <div class="col">
                          <h2>Boolflix</h2>
                      </div>
                      <div class="col">
                            <div class="input-group mb-3">
                                <input type="text" class="form-control" placeholder="Cerca..." aria-label="Cerca..." aria-describedby="button-addon2">
                                <button class="btn btn-outline-secondary" type="button" id="button-addon2"><i class="bi bi-search"></i></button>
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
    name: "Header"
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