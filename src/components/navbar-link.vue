<template>
  <a :href="item.href"
     :class="classObject">
    {{ item.label }}
  </a>
</template>

<script type="text/babel">
  export default {
    props: ['item'],

    computed: {
      classObject () {
        return {
          disabled: this.item.isDisabled,
          active: this.item.isActive
        }
      }
    }
  }
</script>
