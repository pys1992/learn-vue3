<template>
    <div style="width: 500px;height: 500px;">
        <canvas id="myChartLine" width="200" height="200"></canvas>
    </div>
</template>

<script>
import Chart from 'chart.js/auto';

export default {
    mounted() {

        let myChartElement = document.getElementById('myChartLine');

        let backendData = this.fetchData(); // from backend

        let config = {
            type: 'line',
            data: {
                labels: [1, 2, 3, 4, 5, 6, 7],
                datasets: [{
                    label: 'My First Dataset',
                    data: backendData,
                    fill: false,
                    borderColor: 'rgb(75, 192, 192)',
                    tension: 0.1
                }]
            },
        };

        new Chart(myChartElement, config);

    },
    methods: {
        fetchData() {
            // request from api
            return [65, 59, 80, 81, 56, 55, 40];
        }
    },
}
</script>
