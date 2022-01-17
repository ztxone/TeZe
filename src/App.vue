<script setup>
import { ref, watchEffect } from 'vue'
import Header from './components/Header.vue'
import People from './components/People.vue'
import Person from './components/Person.vue'

const showPerson = ref(false)
const clickedPerson = ref({})
const handleClick = (e) => {
  clickedPerson.value = e
  showPerson.value = true
}
watchEffect(() => {
    document.body.style.overflow = showPerson.value ? 'hidden' : ''
  }
)
</script>

<template>
  <Header />
  <main class="relative min-w-[375px]">  
    <div class="flex flex-wrap w-full h-full justify-center items-center gap-12 p-16"
      >
      <People @personCliked="handleClick" />
    </div>    
  </main>
  <div v-if="showPerson" class="fixed top-0 left-0 right-0 bottom-0 bg-black/60 backdrop-blur z-20 flex justify-center items-center" @click.self="showPerson = false">
    <Person :person="clickedPerson" />        
  </div>
</template>

<style>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  background-color: rgb(243 244 246);
}
</style>
