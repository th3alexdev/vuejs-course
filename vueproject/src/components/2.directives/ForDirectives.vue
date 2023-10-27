<template>
  <ul :class="'flex items-center justify-center flex-col gap-2'">
    <!--  
      Basic
      <li v-for="(country, index) in countries" :key="index" class="bg-red-500 px-2  font-bold">
      {{ country }}
      </li> 
    -->

    <li v-for="country in countries" :key="country.code" :class="`${country.color} px-2 font-bold`">
      {{ country.name }}
    </li> 
  </ul>
</template>

<script setup>
import { ref } from 'vue'

let countries = ref([
  {
    code: 've',
    name: 'Venezuela',
    color: 'bg-red-400'
  },
  {
    code: 'es',
    name: 'Spain',
    color: 'bg-yellow-400'
  },
  {
    code: 'ar',
    name: 'Argentina',
    color: 'bg-blue-400'
  },
  {
    code: 'mx',
    name: 'Mexico',
    color: 'bg-green-400'
  }
])
</script>

<style></style>
