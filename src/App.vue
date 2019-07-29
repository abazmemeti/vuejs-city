<template>
  <div id="app">
    <Navbar />
    <ToursList />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import ToursList from './components/ToursList.vue';

export default {
  name: 'app',
  components: {
    Navbar,
    ToursList
  }
}
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
}
</style>
