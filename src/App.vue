<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div>
    <button @click="sidebarSwitch">OPEN</button>
  </div>
  <Sidebar :opened="sidebarIsOpened" @closed="sidebarSwitch"></Sidebar>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Sidebar from './components/sidebar/Sidebar.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld
    Sidebar
  },
  data() {
    return {
      sidebarIsOpened: false
    }
  },
  methods: {
    toPage(x) {
      console.log(x);
    },
    sidebarSwitch() {
      this.sidebarIsOpened = !this.sidebarIsOpened;          
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

  height: 1000vh;
}
</style>
