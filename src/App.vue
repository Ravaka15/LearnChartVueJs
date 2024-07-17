<template>
  <CustomChart4/>
  <CustomChart3/>
  <CustomChart2/>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
 
</template>

<script>
import CustomChart4 from './components/CustomChart4';
import CustomChart3 from './components/CustomChart3.vue';
import CustomChart2 from './components/CustomChart2.vue';
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    CustomChart4,
    CustomChart3,
    CustomChart2,
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
