<template lang="html">
    <main role="main" class="container">
        <h1>Vos dernières consomations</h1>
        <canvas id="chartWater" class="my-4 w-100" width="900" height="380"></canvas>
        <canvas id="chartLightning" class="my-4 w-100" width="900" height="380"></canvas>
        <canvas id="chartHeating" class="my-4 w-100" width="900" height="380"></canvas>
    </main>
</template>

<script>
// TODO: mettre un bouton pour switche chaque graph entre 1 mois et 3 jours
import Chart from 'chart.js';

export default {
    name: 'monitor',
    methods: {
        createChart(charType, data) {
            var ctx = document.getElementById(charType).getContext('2d');
            var chart = new Chart(ctx, {
                // The type of chart we want to create
                type: 'line',

                // The data for our dataset
                data: {
                    labels: ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"],
                    datasets: [{
                        label: "Graphique sur l'année",
                        backgroundColor: 'rgb(255, 99, 132)',
                        borderColor: 'rgb(255, 99, 132)',
                        data: data
                    }]
                },

                // Configuration options go here
                options: {}
            });
        }
    },
    mounted() {
      this.createChart('chartWater', ['40', '40', '40', '780', '400', '40', '40', '40', '100', '40', '40', '40']);
      this.createChart('chartLightning', ['40', '40', '40', '780', '400', '40', '40', '40', '100', '40', '40', '40']);
      this.createChart('chartHeating', ['40', '40', '40', '780', '400', '40', '40', '40', '100', '40', '40', '40']);
    }
}


</script>

<style lang="css" scoped>
</style>
