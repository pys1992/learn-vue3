<template>
    <div style="width: 500px;height: 500px;">
        <canvas id="myChart" width="200" height="200"></canvas>
    </div>
</template>

<script>
import Chart from 'chart.js/auto';

export default {
    mounted() {

        let myChartElement = document.getElementById('myChart');

        let backendData = this.fetchData(); // from backend

        //     [
        //         {
        //             label: 'Label1',
        //             price: 300,
        //         },
        //         {
        //             label: 'Label2',
        //             price: 50,
        //         },
        //         {
        //             label: 'Label3',
        //             price: 100,
        //         },
        //     ];

        // pluck label value
        let myLabels = backendData.map(item => item.label);

        // pluck price value
        let myPrices = backendData.map(item => item.price);

        let myBackgroundColors = [];

        for (let i = 0; i < backendData.length; i++) {
            myBackgroundColors[i] = `rgb(${i}, ${i + 99}, ${i + 120})`;
        }

        let config = {
            type: 'doughnut',
            data: {
                labels: myLabels, // replace 1
                datasets: [{
                    label: 'My First Dataset',
                    data: myPrices, // replace 2
                    backgroundColor: myBackgroundColors, // replace 3
                    hoverOffset: 4
                }]
            },
        };

        let chartInstance = new Chart(myChartElement, config);

    },
    methods: {
        fetchData() {
            // request from api
            return [
                {
                    label: 'Label1',
                    price: 300,
                },
                {
                    label: 'Label2',
                    price: 50,
                },
                {
                    label: 'Label3',
                    price: 100,
                },
            ];
        }
    },
}
</script>
