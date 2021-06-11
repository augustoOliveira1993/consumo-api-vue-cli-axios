<template>
  <div id="app">
    <img alt="Vue logo" class="logo" src=".\assets\coindesk.png">
    <CoindDesk id="con"/>
  </div>
</template>

<script>
import CoindDesk from './components/CoindDesk.vue'

export default {
  name: 'App',
  components: {
    CoindDesk
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

.logo {
  width: 400px;
  height: 300px;
}
</style>
