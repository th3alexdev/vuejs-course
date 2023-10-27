<template>
    <h1 :class="'mb-5 text-6xl'">{{ counter }}</h1>
    <div :class="'flex gap-3 items-center justify-center'">
      <button @click="addCounter" :class="'bg-blue-400 px-4 py-1 font-bold'">Add</button>
      <button @click="subsCounter" :class="'bg-red-400 px-4 py-1 font-bold'">Substract</button>
    </div>
</template>
  
<script>
import { defineComponent, ref } from 'vue';
export default defineComponent({
  name: 'CounterOption',
  components: {},
  props: {},
  setup() {
    let counter = ref(0);

    const addCounter = () => {
      counter.value++
      // console.log(counter)
    }
    const subsCounter = () => {
      counter.value--
    }
    return {counter, addCounter, subsCounter}
  }
})
</script>
  
<style>
      
</style>