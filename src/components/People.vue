<script setup>
import { ref, onMounted } from 'vue'
import Person from './Person.vue'

const url = 'https://api.interview.dev-team.club/people'
const options = { 
  method: 'GET',
  headers: {'Content-Type': 'application/json'} 
}
const loading = ref(true)
const people = ref([])

const getPeople = async () => {
  people.value = await fetch(url, options)
    .then(res => { return res.json() })
    .then(data => { 
      loading.value = false
      return data
    })
    .catch(error => { console.log(error.message) })
}
const emits = defineEmits({
  personCliked: String
})

onMounted(getPeople())

const personCliked = (person) => { 
  emits('personCliked', person)
}
</script>

<template>
  <div class="flex flex-wrap justify-center gap-12 ">
    <Person v-for="person in people" :key="person.Id" 
      :person="person"
      @click="personCliked(person)"
    />
    <div v-if="loading" class="flex flex-col items-center" >
      <span>Data is loading...</span>      
      <span><img src="../assets/img/Spheresdance.gif" alt="loading gif"></span>
    </div>
  </div>
</template>
