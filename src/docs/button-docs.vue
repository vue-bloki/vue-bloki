<template>
  <div>
    <component-docs :docs="docs">

      <label>
        <input type="checkbox" v-model="disabled">Disabled
      </label>

      <label>
        <input type="checkbox" v-model="outline">Outline
      </label>

      <label>
        <input type="radio" value="small" v-model="size">Small
      </label>
      <label>
        <input type="radio" value="medium" v-model="size">Medium
      </label>
      <label>
        <input type="radio" value="large" v-model="size">Large
      </label>

      <div>
        <vb-button :disabled="disabled" :outline="outline" :size="size">Button</vb-button>
        <vb-button :disabled="disabled" :outline="outline" :size="size" variant="primary">Button</vb-button>
        <vb-button :disabled="disabled" :outline="outline" :size="size" variant="success">Button</vb-button>
        <vb-button :disabled="disabled" :outline="outline" :size="size" variant="warning">Button</vb-button>
        <vb-button :disabled="disabled" :outline="outline" :size="size" variant="error">Button</vb-button>
      </div>

    </component-docs>
  </div>
</template>

<script type="text/babel">
  import ComponentDocs from './../components/component-docs.vue'
  import VbButton from './../components/button.vue'

  export default {
    name: 'button-docs',

    data () {
      return {
        disabled: false,
        outline: false,
        size: 'medium',

        docs: {
          title: 'Button',

          props: {
            disabled: {
              type: Boolean,
              default: false
            },

            variant: {
              type: String,
              default: 'default',
              description: 'Applies button style. The value can be `default`, `primary`, `success`, `warning`, `error`.'
            },

            size: {
              type: String,
              default: 'medium'
            },

            outline: {
              type: Boolean,
              default: false
            }
          },

          slots: {
            default: {
              description: 'Default slot that contains button content.'
            }
          },

          events: {
            click: {
              description: 'Click event.'
            }
          }
        }
      }
    },

    components: {
      VbButton,
      ComponentDocs
    }
  }
</script>
