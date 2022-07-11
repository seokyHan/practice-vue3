<template>
  <button @click="message = 'Good?'">
    click!
  </button>
  <h1>App: {{ message }}</h1>
  <Parent />
</template>

<script>
import Parent from '~/components/Parent'
import { computed } from 'vue'

export default {
  components: {
    Parent
  },
  data() {
    return {
      message: 'Hello vue!'
    }
  },
  provide() {
    return {
      msg: computed(() => {
        return this.message
      })
    }
  }
}
</script>

