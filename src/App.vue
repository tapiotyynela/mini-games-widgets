<template>
  <div id="app">
    <Header />
    <NamePicker />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import NamePicker from './components/NamePicker';
export default {
  name: 'App',
  components: {
    Header,
    NamePicker
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
  background: #ff8484;
  margin-top: 60px;
}
body {
    background: #ff8484;
}
</style>
