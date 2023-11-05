<template>
  <p>Text: {{ inputRef }}</p>
  <form>
    <input type="text" class="outline px-2 py-.5 mb-8" v-model="inputRef"/>
    
    <label for="agree" class="block mb-8">
    ¿Aceptas los términos y condiciones?  
      <input type="checkbox" name="" id="agree" v-model="agreeRef">
    </label>

    <select v-model="countryRef">
      <option value="es">Spain</option>
      <option value="ve">Venezuela</option>
      <option value="ar">Argentina</option>
      <option value="mx">Mexico</option>
    </select>
  </form>
</template>

<script setup>
import { ref } from 'vue'
let inputRef = ref('')
let agreeRef = ref(true)
let countryRef = 've' 
</script>

<style scoped>
.outline {
    outline: 1px solid #222;
}
</style>