<template>
  <div>
    <h1>{{ title }}</h1>
    <p>hello, {{ name }}</p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

interface Data {
  title: string
}
export default Vue.extend({
  props: {
    name: {
      type: String,
      required: true
    }
  },
  data(): Data {
    return {
      title: 'Use Component Sample'
    }
  }
})
</script>
