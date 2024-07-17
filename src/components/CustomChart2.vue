<template>
    <div class="chart-container">
      <div 
        v-for="(item, index) in sortedData" 
        :key="index" 
        class="bar" 
        :style="{ width: item.width, backgroundColor: item.color }"
      >
        <span class="label">{{ item.label }}: {{ item.value }}</span>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const data = ref([
    { label: 'Facebook', value: 1880, color: '#00E396' },
    { label: 'Google', value: 1100, color: '#FEB019' },
    { label: 'Trip Advisor', value: 990, color: '#008FFB' },
    { label: 'Booking', value: 880, color: '#00E396' },
    { label: 'Instagram', value: 740, color: '#775DD0' }
  ]);
  
  const maxValue = computed(() => Math.max(...data.value.map(item => item.value)));
  
  const sortedData = computed(() => {
    return data.value
      .map(item => ({
        ...item,
        width: `${(item.value / maxValue.value) * 100}%`
      }))
      .sort((a, b) => b.value - a.value);
  });
  </script>
  
  <style scoped>
  .chart-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    max-width: 600px;
  }
  
  .bar {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 50px;
    margin: 5px 0;
    color: #fff;
    font-size: 16px;
    font-family: Arial, sans-serif;
    position: relative;
  }
  
  .label {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
  }
  </style>
  