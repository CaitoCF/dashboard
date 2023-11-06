<template>
    <DashboardComponent :title="title" :icon="icon">
        <div class="page-content">
            <CardsComponent />
            <canvas id="myChart1" height="80" style="margin-top: 100px;"></canvas>
            <canvas id="myChart2" height="80" style="margin-top: 100px;"></canvas>
        </div>
    </DashboardComponent>
</template>

<script>
import DashboardComponent from '../Dashboard/DashboardComponent.vue';
import CardsComponent from '../../components/Cards/CardsComponent.vue';
import Chart from 'chart.js/auto';

export default {
    name: 'HomeComponent',
    components: { DashboardComponent, CardsComponent },
    data() {
        return {
            title: "Home",
            icon: "fa-house"
        }
    },
    mounted() {
        const canvas1 = document.getElementById('myChart1');
        const myChart = new Chart(canvas1, {
            type: 'line',
            data: {
                labels: ['January', 'Febuary', 'March', 'April', 'May'],
                datasets: [{
                    label: 'Sales per Month',
                    data: [1, 3, 4, 2, 5],
                    backgroundColor: '#d97f76',
                    borderColor: '#b4585d',
                    borderWidth: 2
                }]
            },
            options: {
                scales: {
                    y: {
                        beginAtZero: true   
                    }
                }
            }
        });

        const canvas2 = document.getElementById('myChart2');
        const myChart2 = new Chart(canvas2, {
            type: 'bar',
            data: {
                labels: ['Product1', 'Service2', 'Product5', 'Service1'],
                datasets: [{
                    label: 'Best-Selling of the Year',
                    data: [4, 1, 3, 2],
                    backgroundColor: '#d97f76',
                    borderColor: '#b4585d',
                    borderWidth: 2
                }]
            },
            options: {
                scales: {
                    y: {
                        beginAtZero: true   
                    }
                }
            }
        });

        myChart;
        myChart2;
    }
}
</script>

<style lang="scss" src="./style.scss" scoped />