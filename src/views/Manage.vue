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
          <div class="form-group">
            <select multiple class="form-control text-center" v-model="water" v-on:click="sendDataWater">
              <h3>Consommation d'eau</h3>
              <option class="btn-sm btn-outline-warning" value="70">Haute</option>
              <option class="btn-sm btn-outline-info" value="20">Basse</option>
            </select>
          </div>
        </div>
      </div>
      <div class="card mb-4 shadow-sm">
        <div class="card-header">
          <h4 class="my-0 font-weight-normal">Electricite</h4>
        </div>
        <div class="card-body">
          <h1 class="card-title pricing-card-title"> <small class="text-muted"></small></h1>
          <div class="form-group">
            <select multiple class="form-control text-center" v-model="lightning" v-on:click="sendDataElec">
              <option class="btn-sm btn-outline-success" value="0">0 lux</option>
              <option class="btn-sm btn-outline-primary" value="100">100 Lux</option>
              <option class="btn-sm btn-outline-info" value="200">200 Lux</option>
              <option class="btn-sm btn-outline-warning" value="300">300 Lux</option>
              <option class="btn-sm btn-outline-danger" value="400">400 Lux</option>
            </select>
          </div>
          <ul class="list-unstyled mt-3 mb-4">
            <li>Selectionnez la luminosité dans la pièce</li>
          </ul>
        </div>
      </div>
      <div class="card mb-4 shadow-sm">
        <div class="card-header">
          <h4 class="my-0 font-weight-normal">Chauffage</h4>
        </div>
        <div class="card-body">
          <h1 class="card-title pricing-card-title"><small class="text-muted"></small></h1>

          <div class="form-group">
            <select multiple class="form-control text-center" v-model="tempeature" v-on:click="sendDataTemp">
              <option class="btn-sm btn-outline-success" value="22">Confort</option>
              <option class="btn-sm btn-outline-secondary" value="19">Normal</option>
              <option class="btn-sm btn-outline-primary" value="17">Eco</option>
            </select>
          </div>
          <ul class="list-unstyled mt-3 mb-4">
            <li>Vous pouvez choisir votre mode de chauffage</li>
          </ul>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
  const axios = require("axios");

  export default {
    name: "manage",
    data: function() {
      return {
        tempeature: [],
        lightning: [],
        water: []
      };
    },
    methods: {
      sendDataTemp: function() {
        axios.post(
          "http://api.econhome.ovh/users/temperature",
          {
            data: this.tempeature
          },
          {
            headers: {
              "Access-Control-Allow-Origin": "*"
            }
          }
        );
      },
      sendDataElec: function() {
        axios.post(
          "http://localhost:8081/users/lightning",
          {
            data: this.lightning
          },
          {
            headers: {
              "Access-Control-Allow-Origin": "*"
            }
          }
        );
      },
      sendDataWater: function() {
        axios.post(
          "http://localhost:8081/users/water",
          {
            data: this.water
          },
          {
            headers: {
              "Access-Control-Allow-Origin": "*"
            }
          }
        );
      }
    },
    mounted() {}
  };
</script>

<style lang="css" scoped>
</style>
