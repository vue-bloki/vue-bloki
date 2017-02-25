<template>
  <div>
    <component-docs :docs="docs">

      <VbButton variant="success" @click="show = true">
        Show modal
      </VbButton>

      <modal
        v-if="show"
        @close="show = false"
        title="Modal title">

        <div slot="body">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. A aut dignissimos eaque harum, nobis numquam
          obcaecati? Adipisci alias at, aut delectus est et molestias non praesentium qui quis sapiente totam!
        </div>

        <div slot="footer">
          <VbButton variant="primary" size="small">Lorem</VbButton>
        </div>

      </modal>

    </component-docs>
  </div>
</template>

<script type="text/babel">
  import ComponentDocs from './../components/component-docs.vue'
  import Modal from './../components/modal.vue'
  import VbButton from './../components/button.vue'

  export default {
    name: 'modal-docs',

    data () {
      return {
        show: false,

        docs: {
          title: 'Modal',

          props: {
            title: {
              type: String,
              description: 'Modal title. Nothing more, nothing less.'
            }
          },

          slots: {
            header: {
              description: 'The modal header by default contains title nad close button. The header slot should be used only if you want to override this default content. Can contain HTML and other components.'
            },
            body: {
              description: 'The body slot holds main content of the modal. Can contain HTML and other components.'
            },
            footer: {
              description: 'The footer slot holds the modal footer. Can contain HTML and other components.'
            }
          },

          events: {
            close: {
              description: 'Dispatched when the modal is closed.'
            }
          }
        }
      }
    },

    components: {
      Modal,
      ComponentDocs,
      VbButton
    }
  }
</script>
