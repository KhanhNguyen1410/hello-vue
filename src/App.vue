<template>
  <div id="app">
    <div v-show="isShow">
    <img alt="Vue logo" src="./assets/logo.png">
    </div>
    <button @click=" isShow = ! isShow">click me</button>
    <Demo />
  </div>
</template>

<script>
import Demo from './components/demo.vue'



export default {
  name: 'App',
  components: {
    Demo
  },
    
  data() {
    return {
      isShow : true
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
