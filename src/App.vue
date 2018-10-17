<template>
  <div id="app">
    <vueCanvasNest/>
    <OperaLogo v-if="now === 'op'"/>
    <Sector v-if="now === 'pie'"/>
    <button @click="nextComponent">{{status}}</button>
  </div>
</template>

<script>
import OperaLogo from './components/OperaLogo.vue'
import vueCanvasNest from 'vue-canvas-nest'
import Sector  from  './components/Sector-graph.vue'

export default {
  name: 'app',
  components: {
    OperaLogo,vueCanvasNest,Sector
  },
  data: function(){
      return{
          now: 'op',
          have: ['op', 'pie'],
          status: 'next'
      }
  },
  methods: {
      nextComponent: function(){
          console.log(this.now);
          let index = this.have.indexOf(this.now);
          if(this.status === 'back'){
              this.status = 'next';
              this.now = this.have[0];
          }else if(index + 1=== this.have.length - 1){
              this.now = this.have[index + 1];
              this.status = 'back';
          }
      }
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

  button{
    width: 5%;
    padding:5px 10px ;
    border-radius: 5px;
    border: 0px;
    background-color: #fff;
    color: #000;
    cursor: pointer;
    border: 1px solid #aeacac;
  }

  [disabled]{
    cursor: default;
  }
</style>
