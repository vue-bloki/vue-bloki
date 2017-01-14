<template>
  <div>
    <component-docs :docs="docs">
      <div>
        <notification
          :message="message"
          v-if="show"
          @close="show = false">
        </notification>

        <notification
          :message="message"
          v-if="showPrimary"
          @close="showPrimary = false"
          variant="primary">
        </notification>

        <notification
          :message="message"
          v-if="showSuccess"
          @close="showSuccess= false"
          variant="success">
        </notification>

        <notification
          :message="message"
          v-if="showWarning"
          @close="showWarning = false"
          variant="warning">
        </notification>

        <notification
          :message="message"
          v-if="showError"
          @close="showError = false"
          variant="error">
        </notification>

        <vb-button variant="success" @click="reset">Reset</vb-button>
      </div>
    </component-docs>
  </div>
</template>

<script type="text/babel">
  import ComponentDocs from './../components/component-docs.vue'
  import Notification from './../components/notification.vue'
  import vbButton from './../components/button.vue'

  export default {
    name: 'notification-docs',
    data () {
      return {
        show: true,
        showPrimary: true,
        showSuccess: true,
        showWarning: true,
        showError: true,
        message: `Lorem ipsum dolor sit amet, consectetur adipisicing elit.`,
        docs: {
          title: 'Notification',
          props: {
            message: {
              type: String
            },
            variant: {
              type: String,
              default: 'default',
              description: 'Variants which you can set `default`, `primary`, `success`, `warning`, `error`.'
            }
          }
        }
      }
    },
    methods: {
      reset () {
        this.show = true
        this.showPrimary = true
        this.showSuccess = true
        this.showWarning = true
        this.showError = true
      }
    },
    components: {
      Notification,
      ComponentDocs,
      vbButton
    }
  }
</script>

<style lang="scss" rel="stylesheet/scss">
  .notification {
    margin-bottom: 10px;
  }
</style>
