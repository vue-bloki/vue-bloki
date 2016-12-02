<template>
  <div>
    <h1>{{ docs.title }}</h1>

    <ul>
      <li><a href="#examples">Examples</a></li>
      <li v-if="docs.props"><a href="#props">Props</a></li>
      <li v-if="docs.slots"><a href="#slots">Slots</a></li>
      <li v-if="docs.events"><a href="#events">Events</a></li>
    </ul>

    <div id="examples">
      <h2>Examples</h2>
      <slot></slot>
    </div>

    <div id="props" v-if="docs.props">
      <h2>Props</h2>
      <table>
        <thead>
        <tr>
          <th>Name</th>
          <th>Type</th>
          <th>Default</th>
          <th>Description</th>
        </tr>
        </thead>
        <tbody>
        <tr v-for="(propData, propName) in docs.props">
          <td><code>{{ propName }}</code></td>
          <td><code>{{ propData.type.name }}</code></td>
          <td>
            <code v-if="propData.default !== undefined">{{ propData.default }}</code>
          </td>
          <td>
            <div v-html="marked(propData.description)"></div>
          </td>
        </tr>
        </tbody>
      </table>
    </div>

    <div id="slots" v-if="docs.slots">
      <h2>Slots</h2>
      <table>
        <thead>
        <tr>
          <th>Name</th>
          <th>Description</th>
        </tr>
        </thead>
        <tbody>
        <tr v-for="(slotData, slotName) in docs.slots">
          <td><code>{{ slotName }}</code></td>
          <td>
            <div v-if="slotData.description !== undefined" v-html="marked(slotData.description)"></div>
          </td>
        </tr>
        </tbody>
      </table>
    </div>

    <div id="events" v-if="docs.events">
      <h2>Events</h2>
      <table>
        <thead>
        <tr>
          <th>Name</th>
          <th>Description</th>
        </tr>
        </thead>
        <tbody>
        <tr v-for="(eventData, eventName) in docs.events">
          <td><code>{{ eventName }}</code></td>
          <td>
            <div v-if="eventData.description !== undefined" v-html="marked(eventData.description)"></div>
          </td>
        </tr>
        </tbody>
      </table>
    </div>

  </div>
</template>

<script type="text/babel">
  import marked from 'marked'

  export default {
    props: {
      docs: {
        type: Object
      }
    },

    methods: {
      marked (text) {
        if (text) {
          return marked(text)
        } else {
          return ''
        }
      }
    }
  }
</script>

<style scoped>
  table {
    border-collapse: collapse;
  }

  th, td {
    text-align: left;
    padding: 10px 20px;
    border-color: whitesmoke;
    border-style: none none solid none;
  }

  th {
    border-width: 2px;
  }

  td {
    border-width: 1px;
  }
</style>
