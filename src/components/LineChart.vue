<template>
    <div id="chartContainer">
        <canvas id="myChart" width="800px" height="400px"></canvas>
    </div>
</template>

<script>
import {Chart} from "chart.js/auto";

let myChart;
myChart;

export default {
    name: 'LineChart',
    mounted() {
        this.updateStockPriceHistoryChart()
    },
    setup(){
        let updateStockPriceHistoryChart = () => {
            const ctx = document.getElementById('myChart');

            const labels = ['January','Febuary','March','April','May','June','July','August','September','October','November','December']

            const data = {
                labels: labels,
                datasets: [{
                    label: 'Stock Market',
                    data: [1,5,2,14,3,6,7,1,5,2,14,3,6,7],
                    fill: false,
                    borderColor: 'rgb(75,192,192)',
                    tension: 0,
                    options: {
                        responsive: true,
                        maintainAspectRatio: false,
                    }
                }]
            }

            myChart = new Chart(ctx,{
                type: 'line',
                data: data,
            })
        }

        return {
            updateStockPriceHistoryChart
        }
    }

}

</script>

<style scoped>

</style>
