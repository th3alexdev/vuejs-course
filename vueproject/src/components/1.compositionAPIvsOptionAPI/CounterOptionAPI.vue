<template>
  <h1 :class="'mb-5 text-6xl'">{{ counter }}</h1>
  <div :class="'flex gap-3 items-center justify-center'">
    <button @click="addCounter" :class="'bg-blue-400 px-4 py-1 font-bold'">Add</button>
    <button @click="subsCounter" :class="'bg-red-400 px-4 py-1 font-bold'">Substract</button>
  </div>
</template>

<script>
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'CounterOption',
  components: {},
  props: {},
  data() {
    let counter = 0;
    return {counter}
  },
  methods: {
    addCounter() {
      this.counter++
    },
    subsCounter(){
      this.counter--
    }
  }
})
</script>

<style>
    
</style>