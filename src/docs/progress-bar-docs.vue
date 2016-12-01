<template>
  <div>
    <component-docs :docs="docs">

      <div>
        <button @click="value = 0">0%</button>
        <button @click="value += 10">+10%</button>
        <button @click="value -= 10">-10%</button>
        <button @click="value = 100">100%</button>
      </div>

      <div>
        <label>
          <input type="checkbox" v-model="indeterminate">Indeterminate
        </label>
      </div>

      <div>
        <label>
          <input type="checkbox" v-model="noAnimation">No animation
        </label>
      </div>

      <div>
        <label>
          <input type="checkbox" v-model="noStripes">No stripes
        </label>
      </div>

      <progress-bar
        :value="value"
        :indeterminate="indeterminate"
        :no-stripes="noStripes"
        :no-animation="noAnimation"
      ></progress-bar>

    </component-docs>
  </div>
</template>

<script type="text/babel">
  import ProgressBar from './../components/progress-bar.vue'
  import ComponentDocs from '../components/component-docs.vue'

  export default {
    data () {
      return {
        value: 10,
        indeterminate: false,
        noStripes: false,
        noAnimation: false,

        docs: {
          title: 'Progress bar',

          props: {
            value: {
              type: Number
            },
            indeterminate: {
              type: Boolean,
              default: false
            },
            noStripes: {
              type: Boolean,
              default: false
            },
            noAnimation: {
              type: Boolean,
              default: false
            }
          }
        }
      }
    },

    components: {
      ProgressBar,
      ComponentDocs
    }
  }
</script>
