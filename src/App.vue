<template>
  <div id="app">
    <vueCanvasNest/>
    <OperaLogo v-if="now === 'op'"/>
    <Sector v-if="now === 'pie'"/>
    <button @click="nextComponent">{{status}}</button>
    <router-view></router-view>
    <router-link to="/index">Go to index</router-link>
    <router-link to="/about">Go to about</router-link>
  </div>
</template>

<script>
import VueRouter from 'vue-router'
import OperaLogo from './components/OperaLogo.vue'
import vueCanvasNest from 'vue-canvas-nest'
import Sector  from  './components/Sector-graph.vue'
import index  from  './components/index.vue'
import about  from  './components/about.vue'

let id = {
    render (createElement){
        return createElement('div', this.userInfo);
    },
        beforeRouteUpdate: function(to, from, next){
            this.userInfo = '' + to + from;
            next();
        },
    data:function(){
        return {
            userInfo :'默认'
        }

    }
}
const routers = [
    {
        path: '/index',
        component: index
    },
    {
        path: '/about',
        component: about
    },
    {
        path: '/user/:id',
        component: id
    }
];

const router = new VueRouter({
    mode: 'history',
    routes: routers
});

export default {
  name: 'app',
  router: router,
  components: {
    OperaLogo, vueCanvasNest, Sector, index, about
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
