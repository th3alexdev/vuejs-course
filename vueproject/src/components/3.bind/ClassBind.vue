<template>
  <div :class="'w-max mx-auto flex flex-col items-center justify-center '">
    <p :class="{ 'bg-red-500 px-2 font-bold mb-5': hasError }">Successfully?</p>
    
    <!-- styles on line  -->
    <p :class="'w-max font-bold text-5xl px-2'" :style="{ backgroundColor: '#42b883' }">Vue.js</p> 
  </div>
</template>

<script setup>
let hasError = true; // true or false
</script>

<style>
  
</style>