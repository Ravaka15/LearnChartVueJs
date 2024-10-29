<template>
    <div>
      <button @click="updateChartData">Mettre à jour les données</button>
      <apexchart type="bar" :options="chartOptions" :series="series"></apexchart>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import VueApexCharts from 'vue3-apexcharts'
  
  const chartOptions = ref({
    chart: {
      id: 'basic-bar',
      toolbar: {
        show: false
      }
    },
    plotOptions: {
      bar: {
        horizontal: false,
        columnWidth: '55%',
        endingShape: 'rounded'
      },
    },
    dataLabels: {
      enabled: false
    },
    stroke: {
      show: true,
      width: 2,
      colors: ['transparent']
    },
    xaxis: {
      categories: ['Fév', 'Mar', 'Avr', 'Mai', 'Juin', 'Juil'],
    },
    yaxis: {
      title: {
        text: 'Nombre de visiteurs (milliers)'
      }
    },
    fill: {
      opacity: 1
    },
    tooltip: {
      y: {
        formatter: function (val) {
          return val + " milliers"
        }
      }
    }
  });
  
  const series = ref([{
    name: 'Visiteurs',
    data: [44, 55, 57, 56, 61, 58]
  }]);
  
  function updateChartData() {
    series.value[0].data = series.value[0].data.map(value => Math.floor(Math.random() * 100));
  }
  </script>
  
  <script>
  export default {
    components: {
      apexchart: VueApexCharts
    }
  };
  </script>
  