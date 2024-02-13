<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div>
    <Paginator v-for="i in 100" total-page="100" :current-page="i" @toPage="toPage"></Paginator>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Paginator from './components/paginator/Paginator.vue';

export default {
  name: 'App',
  components: {
    //HelloWorld
    Paginator
  },
  methods: {
    toPage(x) {
      console.log(x);
    }
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
