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
        default: 'default',
        validator (value) {
          return ['default', 'primary', 'success', 'warning', 'error'].includes(value)
        }
      },

      size: {
        type: String,
        default: 'medium',
        validator (value) {
          return ['small', 'medium', 'large'].includes(value)
        }
      },

      outline: {
        type: Boolean,
        default: false
      }
    }
  }
</script>

<style scoped lang="scss" rel="stylesheet/scss">
  @import "./../styles/variables";
  @import '../styles/main';



  button {
    cursor: pointer;
    font-family: inherit;
    font-size: inherit;
    letter-spacing: 0.02em;
    color: white;
    border-radius: 2px;
    border: 2px solid;

    &:focus {
      outline: none;
    }

    &:active {
      box-shadow: 0 0 5px gray;
    }

    &.outline {
      background: transparent;
    }

    &[disabled] {
      opacity: .5;
      cursor: not-allowed;
    }
  }

  .small {
    padding: .3rem .7rem .2rem;
  }

  .medium {
    padding: .5rem 1rem .4rem;
  }

  .large {
    padding: .7rem 1.3rem .5rem;
  }
</style>
