<template>
  <div>
    <component-docs :docs="docs">
      <div>
        <notification :message="message"></notification>
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
