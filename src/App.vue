<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  
  <div class="block">
    <p>Should Refresh</p>
    <p>{{ refreshItem }}</p>
  </div>
  <PullToRefresh @refresh="refresh"></PullToRefresh>
  <div class="block">
    <p>Not Refresh</p>
    <p>{{ notRefreshItem }}</p>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import PullToRefresh from './components/pull-to-refresh/PullToRefresh.vue'


export default {
  name: 'App',
  components: {
    //HelloWorld
    PullToRefresh
  },
  data() {
    return {
      refreshItem: "",
      notRefreshItem: ""
    }
  },
  methods: {
    refresh() {
      this.refreshItem = new Date();
    }
  },
  mounted() {
    let t = new Date();
    this.refreshItem = t;
    this.notRefreshItem = t;
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
  height: 100vh;
}

.block {
  max-width: 400px;
  max-height: 200px;
  width: 100%;
  height: 100%;
  border: 1px solid;
  margin: auto;
  margin-bottom: 1rem;
}

.smallblock {
  width: 100px;
  height: 100px;
  background-color: black;
  margin: auto;
}
</style>
