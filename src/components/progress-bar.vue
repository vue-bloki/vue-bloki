<template>
  <div class="progress-bar">
    <div class="progress" :style="styleObject" :class="classObject"></div>
  </div>
</template>

<script type="text/babel">
  export default {
    props: {
      value: {
        type: Number
      },
      indeterminate: {
        type: Boolean,
        default: false
      },
      noStripes: {
        type: Boolean,
        default: false
      },
      noAnimation: {
        type: Boolean,
        default: false
      }
    },

    computed: {
      classObject () {
        return {
          'without-stripes': this.noStripes,
          'without-animation': this.noAnimation
        }
      },

      styleObject () {
        let width

        if (this.indeterminate) {
          width = 100
        } else if (this.value < 0) {
          width = 0
        } else if (this.value > 100) {
          width = 100
        } else {
          width = this.value
        }

        return {
          width: width + '%'
        }
      }
    }
  }
</script>

<style scoped lang="scss" rel="stylesheet/scss">
  $stripeColor: rgba(255, 255, 255, 0.2);

  @keyframes progress-bar-moves {
    from {
      background-position: 30px 0;
    }
    to {
      background-position: 0 0;
    }
  }

  .progress-bar {
    display: block;
    border-radius: 2px;
    background: rgba(44, 62, 80, 0.2);
    height: 7px;
  }

  .progress {
    background-color: rgba(44, 62, 80, 0.8);
    border-radius: 2px;
    height: 100%;
    transition: width 200ms cubic-bezier(0.4, 1, 0.75, 0.9);

    &:not(.without-stripes) {
      background-image: linear-gradient(
          45deg,
          $stripeColor 25%,
          transparent 25%,
          transparent 50%,
          $stripeColor 50%,
          $stripeColor 75%,
          transparent 75%
      );
      background-size: 30px 30px;
    }

    &:not(.without-animation):not(.without-stripes) {
      animation: progress-bar-moves 300ms linear infinite reverse;
    }
  }
</style>
