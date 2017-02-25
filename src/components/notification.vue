<template>
  <div
    class="notification"
    :class="variant">
    <button
      @click="$emit('close')"
      class="close-btn"></button>
    <p>
      {{message}}
    </p>
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
    }
  }
</script>

<style scoped lang="scss" rel="stylesheet/scss">
  @import '../styles/variables';
  @import '../styles/main';

  .notification {
    border-radius: 3px;
    padding: 16px 20px;
    position: relative;
  }
</style>
