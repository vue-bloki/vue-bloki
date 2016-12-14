<template>
  <transition name="modal">
    <div class="modal-mask">
      <div class="modal-container">

        <div class="modal-header">
          <slot name="header">
            <div class="default-header">
              <div class="modal-title">{{ title }}</div>
              <button class="close-btn" @click="$emit('close')"></button>
            </div>
          </slot>
        </div>

        <div class="modal-body">
          <slot name="body"></slot>
        </div>

        <div class="modal-footer">
          <slot name="footer"></slot>
        </div>

      </div>
    </div>
  </transition>
</template>

<script>
  export default {
    props: {
      title: {
        type: String
      }
    }
  }
</script>

<style scoped lang="scss" rel="stylesheet/scss">
  @import '../styles/main';

  .modal-mask {
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .5);
    display: flex;
    justify-content: center;
    align-items: center;
    transition: opacity .2s ease;
  }

  .modal-container {
    width: 500px;
    margin: 0 auto;
    padding: 20px 30px;
    background-color: #fff;
    border-radius: 2px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
    transition: transform .2s ease;
  }

  .default-header {
    display: flex;
    justify-content: flex-end;
  }

  .modal-title {
    margin-right: auto;
    font-weight: bold;
  }

  .modal-body,
  .modal-footer {
    margin-top: 20px;
    &:empty {
      display: none;
    }
  }

  .modal-enter,
  .modal-leave-active {
    opacity: 0;
  }

  .modal-enter .modal-container,
  .modal-leave-active .modal-container {
    transform: scale(1.1);
  }
</style>
