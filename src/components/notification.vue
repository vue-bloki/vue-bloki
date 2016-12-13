<template>
  <div class="notification">
    <button class="delete"></button>
    {{message}}
  </div>
</template>

<script>
  export default {
    props: {
      message: {
        type: String
      }
    }
  }
</script>

<style scoped lang="scss" rel="stylesheet/scss">
  .notification {
    background-color: whitesmoke;
    border-radius: 3px;
    padding: 16px 20px;
    position: relative;

    & .delete{
      -webkit-touch-callout: none;
      -webkit-user-select: none;
      -moz-user-select: none;
      -ms-user-select: none;
      user-select: none;
      -moz-appearance: none;
      -webkit-appearance: none;
      background-color: rgba(10, 10, 10, 0.1);
      border: none;
      cursor: pointer;
      display: inline-block;
      height: 24px;
      outline: none;
      position: relative;
      vertical-align: top;
      width: 24px;
      border-radius: 0 3px;
      float: right;
      margin: -16px -20px 0 20px;
    }
  }

  *:before, *:after {
    box-sizing: inherit;
  }

  .delete:before, .delete:after {
    background-color: white;
    content: "";
    display: block;
    height: 2px;
    left: 50%;
    margin-left: -25%;
    margin-top: -1px;
    position: absolute;
    top: 50%;
    width: 50%;
  }

  .delete:before {
    -webkit-transform: rotate(45deg);
    transform: rotate(45deg);
  }

  .delete:after {
    -webkit-transform: rotate(-45deg);
    transform: rotate(-45deg);
  }
</style>
