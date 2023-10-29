<!-- BindEvents.vue but with Composition API -->
<template>
  <div class="flex flex-col justify-center items-center">
    <p
      class="w-max px-4 font-bold text-4xl mb-5"
      :style="{ backgroundColor: currentColor }"
    >
      Colorful Title ;)
    </p>
    <button
      class="btn-outline px-2 rounded-sm hover:bg-gray-200"
      v-on:click="handleClick()"
    >
      Change color
    </button>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'
export default defineComponent({
  setup () {
    let colors = ['#ff6961', '#77dd77', '#fdfd96', '#84b6f4', '#fdcae1'];
    let currentColor = ref(colors[0]);

    const randomColor = () => {
      const randomIndex = Math.floor(Math.random() * colors.length)
      return currentColor.value = colors[randomIndex]
    }

    const handleClick = () => randomColor()

    return { currentColor, handleClick }
  }
})

</script>

<style></style>
