<template>
  <button :disabled="disabled"
          :class="[variant, size, {outline: outline}]"
          @click="$emit('click')">
    <slot></slot>
  </button>
</template>

<script type="text/babel">
  export default {
    props: {
      disabled: {
        type: Boolean,
        default: false
      },

      variant: {
        type: String,
        default: 'default'
      },

      size: {
        type: String,
        default: 'medium'
      },

      outline: {
        type: Boolean,
        default: false
      }
    }
  }
</script>

<style scoped lang="scss" rel="stylesheet/scss">
  @import '../styles/main';

  button {
    cursor: pointer;
    font-family: inherit;
    font-size: inherit;
    padding: .5rem 1rem .4rem;
    letter-spacing: 0.02em;
    color: white;
    border: none;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
    border-radius: 2px;
    text-shadow: 0px 1px 2px rgba(0, 0, 0, 0.2);

    &:focus {
      outline-color: lighten(#2c3e50, 25%);
    }

    &.outline {
      background: transparent;
      border-width: 2px;
      border-style: solid;
      text-shadow: none;
      color: inherit;
    }

    &[disabled] {
      opacity: .5;
      cursor: not-allowed;
    }
  }



  .large {
    padding: .7rem 1.3rem .5rem;
  }
</style>
