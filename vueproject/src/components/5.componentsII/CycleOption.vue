<template>
  <div>Hello World</div>
</template>

<script>
import { defineComponent } from 'vue'
export default defineComponent({
  name: 'CycleOption',
  data() {

  },
  methods() {},
  created() { // When the component is created.
    console.log('created');
  },
  mounted() { // When the component has been mounted
    console.log('mounted')
  },
  updated() { // When the component has been updated
    console.log('updated')
  },
  unmounted() { // When the component has been unmounted
    console.log('unmounted')
  },
})
</script>

<style scoped>
</style>