<template>
  <CustomChart7/>
  <CustomChart6/>
  <CustomChart5/>
  <CustomChart4/>
  <CustomChart3/>
  <CustomChart2/>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
 
</template>

<script>
import CustomChart6 from './components/CustomChart6.vue';
import CustomChart5 from './components/CustomChart5.vue';
import CustomChart4 from './components/CustomChart4';
import CustomChart3 from './components/CustomChart3.vue';
import CustomChart2 from './components/CustomChart2.vue';
import HelloWorld from './components/HelloWorld.vue'
import CustomChart7 from './components/CustomChart7.vue';


export default {
  name: 'App',
  components: {
    CustomChart7,
    CustomChart6,
    CustomChart5,
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
