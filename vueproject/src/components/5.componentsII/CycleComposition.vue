<template>
  <div>Hello World in Composition API</div>
</template>

<script setup>
import { onMounted, onUpdated } from 'vue'

onUpdated(() => {
  console.log('updated') // When the component has been updated
}),
onMounted(() => {
  console.log('Mounted') // When the component has been mounted
}) 
</script>

<style scoped>
</style>