<template>
  <div>
    <apexchart type="bar" height="350" :options="chartOptions" :series="series"></apexchart>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import VueApexCharts from 'vue3-apexcharts'

const chartOptions = ref({
  chart: {
    id: 'social-media-chart',
    stacked: true,
    toolbar: {
      show: false
    }
  },
  plotOptions: {
    bar: {
      horizontal: true,
      borderRadius: 10,
      dataLabels: {
        position: 'center', // Centre les labels
      }
    }
  },
  dataLabels: {
    enabled: true,
    formatter: function (val, opts) {
      return opts.w.globals.labels[opts.dataPointIndex] + ': ' + val
    },
    style: {
      colors: ['#fff'],
      fontSize: '16px',
      fontFamily: 'Helvetica, Arial, sans-serif',
      fontWeight: 400
    }
  },
  xaxis: {
    categories: ['Facebook', 'Google+', 'Trip Advisor', 'Booking', 'Instagram'],
    labels: {
      show: false // Cache les labels sur l'axe pour éviter la duplication
    }
  },
  yaxis: {
    labels: {
      style: {
        colors: ['#999'],
        fontSize: '14px'
      }
    }
  },
  colors: ['#2ecc71', '#3498db', '#9b59b6', '#f1c40f', '#e74c3c'], // Couleurs personnalisées
  legend: {
    show: false // Cache la légende
  }
})

const series = ref([{
  data: [1380, 1100, 990, 880, 740]
}])
</script>

<script>
export default {
  components: {
    apexchart: VueApexCharts
  }
};
</script>

<style scoped>
/* Styles personnalisés pour le graphique */
</style>
