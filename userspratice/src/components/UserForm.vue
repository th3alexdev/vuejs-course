<template>
  <h1 class="font-bold text-3xl mb-4">Your User</h1>
  <div class="grid grid-cols-2 h-2/4 py-8">
    <section class="px-8"> <!-- UserDetails -->
      <form action="#" class="flex flex-col gap-4" @submit="(e) => { e.preventDefault() }">
        <div class="flex gap-2">
          <input type="text" id="name" placeholder="Username..." class="outline-input w-full py-3 px-2" v-model="user.nickname" />
        </div>
        <div class="flex gap-2">
          <input type="text" id="name" placeholder="Name..." class="outline-input w-full py-3 px-2" v-model="user.name" />
          <input type="text" id="lastname" placeholder="Last Name..." class="outline-input w-full py-3 px-2" v-model="user.lastname" />
        </div>
        <div class="grid grid-cols-[20%_73%_10%] gap-2 items-center">
          <label for="skills" class="px-2 font-bold">SKILLS</label>
          <input type="text" id="skills" class="outline-input py-1 px-2" v-model="skillsRef" placeholder="Enter a skill..." />
          <button class="w-6" @click="handleAdd()"><img src="../../public/addIcon.svg" alt="Add Button"></button>
          <div v-if="user.skills.length > 0" class="w-full grid col-start-2">
            <ul class="grid gap-3 text-left">
              <li @click="(e) => handleRemove(e)" v-for="(skill, index) in user.skills" :key="index" class="px-2 flex justify-between pr-3">{{ skill }}
                <button><img src="../../public/trashIcon.svg" alt="Remove Skill" data-index="index"></button>
              </li>
            </ul>
          </div>
        </div>
        <div class="grid grid-cols-[21%_78%]">
          <h2 class="font-bold">TYPE </h2>
          <div class="flex gap-5">
            <div class="flex gap-2">
              <input type="radio" id="isFrontend" name="userType" v-model="user.type" value="Front-end"/>
              <label for="isFrontend">Front-end</label>
            </div>
            <div class="flex gap-2">
              <input type="radio" id="isBack" name="userType" v-model="user.type" value="Back-end"/>
              <label for="isBack">Back-end</label>
            </div>
            <div class="flex gap-2">
              <input type="radio" id="isFullStack" name="userType" v-model="user.type" value="FullStack"/>
              <label for="isFullStack">Full Stack</label>
            </div>
          </div>
        </div>
      </form>
    </section>
    <section class="px-8"> <!-- UserSummary -->
      <div class="text-left font-mono">
        <pre>"{{ user.nickname }}": &#123;</pre>
        <pre>  "name": "{{ user.name }}",</pre>
        <pre>  "lastname": "{{ user.lastname }}",</pre>
        <pre>  "skills": [<span v-for="(skill, index) in user.skills" :key="index">{{ index > 0 ? ',' : '' }}<br />&#09;"{{ skill }}"</span></pre>
        <pre>&#32;&#32;],</pre>
        <pre>  "type": {{ user.type }},</pre>
        <pre>  "github": "<a href="https://github.com/th3alexdev" class="underline">github.com/{{ user.nickname }}</a>"</pre>
        <pre>&#125;</pre>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const user = ref({
  nickname: '',
  name: '',
  lastname: '',
  type: 'undefined',
  skills: ['123', 'alex', 'uwu']
})

const skillsRef = ref('')

const handleAdd = () => {
  if (skillsRef.value) {
    user.value.skills.push(skillsRef.value)
    skillsRef.value = ''
  }
}

const handleRemove = (e) => {
  if (e.target.tagName === 'IMG') {
    const index = e.target.getAttribute('data-index')
    if (index !== null) {
      const skillIndex = parseInt(index)
      user.value.skills.splice(skillIndex, 1)
    }
  }
}

</script>

<style scoped>
</style>
