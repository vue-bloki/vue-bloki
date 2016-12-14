<template>
  <div id="app">
    <layout>
      <navbar slot="sidebar" :items="menuItems"></navbar>
      <content-wrapper slot="content">
        <router-view></router-view>
      </content-wrapper>
    </layout>
  </div>
</template>

<script type="text/babel">
  import Layout from './components/layout.vue'
  import Navbar from './components/navbar.vue'
  import ContentWrapper from './components/content-wrapper.vue'

  export default {
    name: 'app',

    components: {
      Layout,
      Navbar,
      ContentWrapper
    },

    data () {
      return {
        menuItems: [
          {
            label: 'Progress bar',
            href: '/#/progress-bar'
          },
          {
            label: 'Modal',
            href: '/#/modal'
          },
          {
            label: 'Card',
            href: '/#/card'
          },
          {
            label: 'Notification',
            href: '/#/notification'
          },
          {
            label: 'Button',
            href: '/#/button'
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

  p {
    margin: 0;
  }

  code {
    border: 1px solid lightgray;
    background: whitesmoke;
    padding: 0 3px;
    border-radius: 2px;
  }

</style>
