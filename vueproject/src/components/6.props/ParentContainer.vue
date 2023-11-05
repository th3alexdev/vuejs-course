<template>
  <section class="flex justify-center items-center">
    <div class="flex flex-col gap-2">
      <ChildCard v-for="dev in devsInfo" :key="dev.id" :dev="dev" @sayHello="greetDev" />
    </div>
  </section>
</template>

<script setup>
import ChildCard from './ChildCard.vue'
let devsInfo = [
  {
    id: 0,
    name: 'Alexander',
    lastname: 'Pérez',
    username: 'th3alexdev',
    nickname: 'Alex',
    stack: ['JavaScript', 'React', 'Vue', 'Java']
  },
  {
    id: 1,
    name: 'Francisco',
    lastname: 'Gómez',
    username: 'codigoconarte',
    nickname: 'Fran',
    stack: ['Java', 'HTML', 'CSS']
  },
  {
    id: 2,
    name: 'Nelson',
    lastname: 'García',
    username: 'garnelson',
    nickname: 'Nelson',
    stack: ['Python', 'Django', 'Laravel']
  }
]

const greetDev = (devname) => {
  alert(`Hello ${devname}!`)
}
</script>

<style scoped>
</style>