<template lang="html">
    <div class="container">
  <div class="card-deck mb-3 text-center">
    <div class="card mb-4 shadow-sm">
      <div class="card-header">
        <h4 class="my-0 font-weight-normal">Eau</h4>
      </div>
      <div class="card-body">
          <h3>Vous consommez</h3>
        <h1 class="card-title pricing-card-title">5L<small class="text-muted">/min</small></h1>
        <ul class="list-unstyled mt-3 mb-4">
          <li>Vous devriez réduire votre consomation d'eau</li>
        </ul>
      </div>
    </div>
    <div class="card mb-4 shadow-sm">
      <div class="card-header">
        <h4 class="my-0 font-weight-normal">Electricite</h4>
      </div>
      <div class="card-body">
        <h1 class="card-title pricing-card-title"> <small class="text-muted"></small></h1>
        <button type="button" class="btn btn-lg col-md-4 btn-outline-success mr-2">On</button>
        <button type="button" class="btn btn-lg col-md-4 btn-outline-danger">Off</button>
        <ul class="list-unstyled mt-3 mb-4">
          <li>Vous pouvez allumer ou couper l'electricite</li>
        </ul>
      </div>
    </div>

    <div class="card mb-4 shadow-sm">
      <div class="card-header">
        <h4 class="my-0 font-weight-normal">Chauffage</h4>
      </div>
      <div class="card-body">
        <h1 class="card-title pricing-card-title"><small class="text-muted"></small></h1>
        <ul class="list-unstyled mt-3 mb-4">
          <li></li>
        </ul>
        <input type="range" class="custom-range" min="0" max="25" value="3" id="customRange2">
      </div>
    </div>

  </div>
</div>
</template>

<script>
export default {
    name: 'manage',
    methods: {},
    mounted() {}
}
</script>

<style lang="css" scoped>
</style>
