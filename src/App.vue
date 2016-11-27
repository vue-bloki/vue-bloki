<template>
  <div id="app">
    <layout>

    </layout>
  </div>
</template>

<script type="text/babel">
  import Layout from './components/layout.vue'

  export default {
    name: 'app',

    components: {
      Layout
    }
  }
</script>

<style>
  * {
    box-sizing: border-box;
  }

  html, body, #app {
    height: 100%;
  }

  body {
    margin: 0;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }
</style>
