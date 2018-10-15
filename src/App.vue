<template>
  <div id="app">
    <vueCanvasNest/>
    <OperaLogo/>
  </div>
</template>

<script>
import OperaLogo from './components/OperaLogo.vue';
import vueCanvasNest from 'vue-canvas-nest'

export default {
  name: 'app',
  components: {
    OperaLogo,vueCanvasNest
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
