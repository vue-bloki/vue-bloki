<template>
  <div>
    <component-docs :docs="docs">
      <div>
        <notification
          :message="message">
        </notification>

        <notification
          :message="message"
          variant="primary">
        </notification>

        <notification
          :message="message"
          variant="success">
        </notification>

        <notification
          :message="message"
          variant="warning">
        </notification>

        <notification
          :message="message"
          variant="error">
        </notification>

      </div>
    </component-docs>
  </div>
</template>

<script type="text/babel">
  import ComponentDocs from './../components/component-docs.vue'
  import Notification from './../components/notification.vue'

  export default {
    name: 'notification-docs',
    data () {
      return {
        message: `Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aperiam consequuntur dolore dolores eos!`,
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

    components: {
      Notification,
      ComponentDocs
    }
  }
</script>

<style scoped lang="scss" rel="stylesheet/scss">
  .notification {
    margin-bottom: 10px;
  }
</style>
