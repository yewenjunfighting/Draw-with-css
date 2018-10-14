<template>
  <div id="app">
    <OperaLogo/>
  </div>
</template>

<script>
import OperaLogo from './components/OperaLogo.vue'

export default {
  name: 'app',
  components: {
    OperaLogo
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
