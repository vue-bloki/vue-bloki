<template>
  <div class="notification"
       v-if="show"
       :class="variant">
    <button @click="close" class="close-btn"></button>
    {{message}}
  </div>
</template>

<script>
  export default {
    props: {
      message: {
        type: String
      },
      variant: {
        type: String,
        default: 'default'
      }
    },
    data () {
      return {
        show: true
      }
    },
    methods: {
      close () {
        this.$emit('close')
        this.show = false
      }
    }
  }
</script>

<style scoped lang="scss" rel="stylesheet/scss">
  @import '../styles/main';

  .notification {
    border-radius: 3px;
    padding: 16px 20px;
    position: relative;
  }
</style>
