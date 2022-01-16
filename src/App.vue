<script setup>
import { ref } from 'vue'
import Header from './components/Header.vue'
import People from './components/People.vue'
import Person from './components/Person.vue'

const showPerson = ref(false)
const clickedPerson = ref({})
const handleClick = (e) => {
  clickedPerson.value = e
  showPerson.value = true
}

</script>

<template>
<main class="bg-gray-100 pt-2 " >
  <Header />
  <div class="flex w-full h-full justify-center items-center p-16" :class="showPerson ? 'fixed' : '' ">
    <People @personCliked="handleClick" />
  </div>
    <div v-if="showPerson" class="fixed w-full h-full top-0 left-0 right-0 bottom-0 bg-black/60 backdrop-blur z-20 overflow-hidden flex justify-center items-center transition-all duration-400" @click.self="showPerson = false">
        <Person :person="clickedPerson" />        
    </div>
</main>
</template>

<style>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
