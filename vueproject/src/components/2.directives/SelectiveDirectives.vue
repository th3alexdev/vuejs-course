<template>
  <h1 v-if="age < 18">MENOR DE EDAD!</h1>
  <h1 v-else>MAYOR DE EDAD!</h1>
</template>

<script setup>
let age = -2

</script>

<style scoped>
    
</style>