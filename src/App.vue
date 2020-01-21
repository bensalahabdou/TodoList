<template>
  <div id="app">
    <h1>TODO LIST</h1>
    <Test></Test>
  </div>
</template>

<script>
import Test from './components/Test'

export default {
  name: 'app',
  components: {
    Test
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  /* margin-top: 60px; */
}
h1 {
  text-align: center;
  background-color: cornflowerblue
}

</style>
