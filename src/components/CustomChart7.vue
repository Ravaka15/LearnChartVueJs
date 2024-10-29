<template>
    <div>
      <button @click="updateChartData">Mettre à jour les données</button>
      <apexchart 
        type="candlestick" 
        height="460" 
        :options="chartOptions" 
        :series="series">
      </apexchart>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import VueApexCharts from 'vue3-apexcharts';
  
  // Options du graphique
  const chartOptions = ref({
    chart: {
      id: 'candlestick-chart',
      toolbar: {
        show: false
      }
    },
    plotOptions: {
      candlestick: {
        colors: {
          upward: '#00b746',
          downward: '#ff0054'
        }
      }
    },
    xaxis: {
      type: 'category',
      categories: ['Fév', 'Mar', 'Avr', 'Mai', 'Juin', 'Juil'],
    },
    yaxis: {
      title: {
        text: 'Nombre de visiteurs (milliers)'
      }
    },
    tooltip: {
      shared: true,
      intersect: false,
      y: {
        formatter: (val) => val + " milliers"
      }
    }
  });
  
  // Données du graphique
  const series = ref([{
    name: 'Visiteurs',
    data: [
      { x: 'Fév', y: [30, 40, 25, 35] },
      { x: 'Mar', y: [30, 50, 20, 45] },
      { x: 'Avr', y: [45, 55, 35, 50] },
      { x: 'Mai', y: [50, 60, 40, 55] },
      { x: 'Juin', y: [60, 70, 50, 65] },
      { x: 'Juil', y: [58, 68, 48, 62] }
    ]
  }]);
  
  // Fonction pour mettre à jour les données du graphique
  function updateChartData() {
    series.value[0].data = series.value[0].data.map(item => ({
      x: item.x,
      y: [
        Math.floor(Math.random() * 100), // Open
        Math.floor(Math.random() * 100), // Close
        Math.floor(Math.random() * 100), // Low
        Math.floor(Math.random() * 100)  // High
      ]
    }));
  }
  </script>
  
  <script>
  export default {
    components: {
      apexchart: VueApexCharts
    }
  };
  </script>
  