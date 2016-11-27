<template>
  <div id="app">
    <layout>
      <navbar slot="sidebar" :items="menuItems"></navbar>
    </layout>
  </div>
</template>

<script type="text/babel">
  import Layout from './components/layout.vue'
  import Navbar from './components/navbar.vue'

  export default {
    name: 'app',

    components: {
      Layout,
      Navbar
    },

    data () {
      return {
        menuItems: [
          {
            label: 'Home',
            href: '/'
          },
          {
            label: 'About',
            href: '/about'
          },
          {
            label: 'Disabled item',
            isDisabled: true
          },
          {
            label: 'Active item',
            href: '/',
            isActive: true
          }
        ]
      }
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
