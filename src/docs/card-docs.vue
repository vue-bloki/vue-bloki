<template>
  <div>
    <component-docs :docs="docs">
      <div>
        <card

        >
        </card>
      </div>
    </component-docs>
  </div>
</template>

<script type="text/babel">
  import ComponentDocs from './../components/component-docs.vue'
  import Card from './../components/card.vue'

  export default {
    name: 'card-docs',
    data () {
      return {
        docs: {
          title: 'Card',
          props: {}
        }
      }
    },

    components: {
      Card,
      ComponentDocs
    }
  }
</script>

<style scoped lang="scss" rel="stylesheet/scss">
</style>
