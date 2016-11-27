<template>
  <div class="navbar">
    <ul>
      <li v-for="item in items">
        <navbar-link :item="item"></navbar-link>
      </li>
    </ul>
  </div>
</template>

<script type="text/babel">
  import NavbarLink from './navbar-link.vue'

  export default {
    components: {
      NavbarLink
    },

    props: {
      items: {
        type: Array
      }
    }
  }
</script>

<style scoped lang="scss" rel="stylesheet/scss">
  .navbar {
    background-color: whitesmoke;
    height: 100%;
  }

  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }

  a {
    padding: 20px;
    display: block;
    color: inherit;
    text-decoration: none;
    transition: background-color 0.2s;

    &:hover {
      background-color: lightgray;
    }

    &.disabled {
      pointer-events: none;
      opacity: 0.5;
    }

    &.active {
      color: white;
      background-color: #2c3e50;
    }
  }
</style>
