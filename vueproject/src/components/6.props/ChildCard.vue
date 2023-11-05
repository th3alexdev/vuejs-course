<template>  
  <div>
    <pre class="hover:underline cursor-pointer bg-red-500 inline text-[8px] px-1 text-gray-200">github.com/{{ props.dev.username }}</pre>
    <p class="font-bold" @click="handleClick">{{ props.dev.name }} {{ props.dev.lastname }}</p>
</div>
</template>

<script> 
import { defineComponent } from 'vue'
export default defineComponent({
  name: 'ChildCard',
  props: {
    dev: Object,
  },
  emits: ['sayHello'],
  setup(props, { emit }) {
    const handleClick = () => {
      emit('sayHello', props.dev.name)
    }
    return { props, handleClick }
  }
})
</script>

<style scoped>
</style>