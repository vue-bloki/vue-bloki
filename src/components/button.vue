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
  @mixin button-variant($topColor, $bottomColor) {
    background: linear-gradient(to bottom, $topColor 0%, $bottomColor 100%);

    &:not([disabled]):hover {
      background: linear-gradient(to bottom, darken($topColor, 5%) 0%, darken($bottomColor, 5%) 100%);
    }

    &.outline {
      border-color: $topColor;
      padding: calc(.5rem - 2px) calc(1rem - 2px) calc(.4rem - 2px);
    }
  }

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

  .default {
    @include button-variant(#515f6e, #2c3e50);
  }

  .primary {
    @include button-variant(#2298c9, #0084b4);
  }

  .success {
    @include button-variant(#89c042, #76af30);
  }

  .warning {
    @include button-variant(#e9c00e, #d8a012);
  }

  .error {
    @include button-variant(#ea0f3b, #c71f3e);
  }

  .small {
    padding: .3rem .7rem .2rem;
  }

  .large {
    padding: .7rem 1.3rem .5rem;
  }
</style>
