<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{msg}}</h1>
   <alert></alert>
  </div>
</template>

<script>
import Alert from './Alert.vue'


export default {
  components: {Alert},
  data() {
    return {
      msg: 'Hello Vue'
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
</style>
