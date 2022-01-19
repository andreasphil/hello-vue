<template>
  <div id="app">
    <hello-world/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
body {
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  background-color: #000;
  font-family: "Interstate", -apple-system, Helvetica, Arial, sans-serif;
  font-size: 16px;
  margin: 0;
  padding: 0;
}

#app {
  font-weight: bold;
  margin: auto;
  max-width: 640px;
  padding: 75px;
  text-align: center;
}
</style>
