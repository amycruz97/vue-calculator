<template>
  <div id="app">
    <Display></Display>
  </div>
</template>

<script>
import Display from './components/Display'

export default {
  name: 'App',
  components: {
 Display,
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
