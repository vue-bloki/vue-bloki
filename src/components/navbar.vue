<template>
  <div class="navbar">
    <ul>
      <router-link
        v-for="item in items"
        :to="item.href"
        :class="{disabled : item.isDisabled}"
        :exact="item.href == '/' "
        tag="li"
        active-class="active">
          <span>
            {{ item.label }}
          </span>
      </router-link>
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

<style lang="scss" rel="stylesheet/scss">
  .navbar {
    background-color: whitesmoke;
    height: 100%;

    ul {
      margin: 0;
      padding: 0;
      list-style-type: none;
    }

    li {
      cursor: pointer;
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
  }
</style>
