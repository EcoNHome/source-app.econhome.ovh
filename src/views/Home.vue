<template lang="html">
    <main role="main" class="container">
        <h1>Vos dernières consomations</h1>
        <p>{{ data }}</p>
        <canvas id="myChart" class="my-4 w-100" width="900" height="380"></canvas>
    </main>
</template>

<script>
import Chart from 'chart.js';
const axios = require('axios');

export default {
    name: 'home',
    methods: {
        createChart() {
            var ctx = document.getElementById('myChart').getContext('2d');
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
                        data: [50, 45, 35, 400, 25, 10, 10, 10, 10, 20, 30, 40]
                    }]
                },

                // Configuration options go here
                options: {}
            });
        }
    },
    mounted() {
        this.createChart(),
        axios
            .get('localhost:8080/', { headers: { "Access-Control-Allow-Origin": "*" } })
            .then(response => (this.dataShow = response))
    },
    data: {
        dataShow: null
    }
}
</script>

<style lang="css" scoped>
</style>
