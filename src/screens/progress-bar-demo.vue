<template>
  <div>
    <button @click="value = 0">0%</button>
    <button @click="value += 10">+10%</button>
    <button @click="value -= 10">-10%</button>
    <button @click="value = 100">100%</button>
    <label>
      <input type="checkbox" v-model="indeterminate">Indeterminate
    </label>
    Current value: {{ value }}
    Indeterminate: {{ indeterminate }}
    <progress-bar :value="value" :indeterminate="indeterminate"></progress-bar>
    <progress-bar :value="value" :indeterminate="indeterminate" :no-animation="true"></progress-bar>
    <progress-bar :value="value" :indeterminate="indeterminate" :no-stripes="true"></progress-bar>
  </div>
</template>

<script type="text/babel">
  import ProgressBar from './../components/progress-bar.vue'

  export default {
    data () {
      return {
        value: 10,
        indeterminate: false
      }
    },

    components: {
      ProgressBar
    }
  }
</script>
