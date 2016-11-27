<template>
  <div>
    <button @click="show = true">
      Show modal
    </button>

    <modal
      v-if="show"
      @close="show = false"
      title="Modal title">

      <div slot="body">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. A aut dignissimos eaque harum, nobis numquam
        obcaecati? Adipisci alias at, aut delectus est et molestias non praesentium qui quis sapiente totam!
      </div>

      <div slot="footer">
        <button>Lorem</button>
      </div>

    </modal>
  </div>
</template>

<script type="text/babel">
  import Modal from './../components/modal.vue'

  export default {
    data () {
      return {
        show: false
      }
    },

    components: {
      Modal
    }
  }
</script>
