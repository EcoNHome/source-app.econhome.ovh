<template lang="html">
    <main role="main" class="container">
        <h1>Vos dernières consomations</h1>
        <canvas id="chart" class="my-4 w-100" width="900" height="380"></canvas>
    </main>
</template>

<script>
import Chart from "chart.js";
import axios from "axios";

export default {
  name: "home",
  methods: {
    createChart(charType, data) {
      var ctx = document.getElementById("chart").getContext("2d");
      var chart = new Chart(ctx, {
        // The type of chart we want to create
        type: "line",

        // The data for our dataset
        data: {
          labels: [
            "January",
            "February",
            "March",
            "April",
            "May",
            "June",
            "July",
            "August",
            "September",
            "October",
            "November",
            "December"
          ],
          datasets: [
            {
              label: "Graphique sur l'année",
              backgroundColor: "rgb(255, 99, 132)",
              borderColor: "rgb(255, 99, 132)",
              data: data
            }
          ]
        },

        // Configuration options go here
        options: {}
      });
    }
  },
  mounted() {
    this.createChart("chartWater", [
      "500",
      "464",
      "400",
      "454",
      "200",
      "0",
      "0",
      "0",
      "30",
      "300",
      "400",
      "500"
    ])
  }
};
</script>

<style lang="css" scoped>
</style>
