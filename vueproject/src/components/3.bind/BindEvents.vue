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
      @click="handleClick()"
    >
      Change color
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
let colors = ['#ff6961', '#77dd77', '#fdfd96', '#84b6f4', '#fdcae1'];
let currentColor = ref(colors[0]);

const randomColor = () => {
  const randomIndex = Math.floor(Math.random() * colors.length);
  currentColor.value = colors[randomIndex];
};

const handleClick = () => randomColor();
</script>

<style>
.btn-outline {
  outline: 1px solid rgba(0, 0, 0, 0.155);
}
</style>
