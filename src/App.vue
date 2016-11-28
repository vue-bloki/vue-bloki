<template>
  <div id="app">
    <layout>
      <navbar slot="sidebar" :items="menuItems"></navbar>
      <content-wrapper slot="content">
        <modal-demo></modal-demo>
      </content-wrapper>
    </layout>
  </div>
</template>

<script type="text/babel">
  import Layout from './components/layout.vue'
  import Navbar from './components/navbar.vue'
  import ContentWrapper from './components/content-wrapper.vue'
  import ModalDemo from './screens/modal-demo.vue'

  export default {
    name: 'app',

    components: {
      Layout,
      Navbar,
      ContentWrapper,
      ModalDemo
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
