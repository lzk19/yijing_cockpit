<template>
  <div id="app">
    <Cockpit/>
  </div>
</template>

<script>
import Cockpit from './views/cockpit/index.vue'

export default {
  name: 'App',
  components: {
    Cockpit
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
