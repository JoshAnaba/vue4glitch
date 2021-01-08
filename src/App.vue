<template>
  <div id="app">
    <AppLayout/>
  </div>
</template>

<script>
import AppLayout from './components/AppLayout.vue'

export default {
  name: 'App',
  components: {
    AppLayout
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans+Condensed:wght@300&display=swap');
#app {
font-family: 'Open Sans Condensed', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  letter-spacing: 5px;
  
}
</style>
