<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Men name="xiaoming"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import Men from './components/Men.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Men
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
