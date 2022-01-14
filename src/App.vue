<script setup>
import Header from './components/Header.vue'
import People from './components/People.vue'
import Person from './components/Person.vue'
</script>

<template>
  <Header />
  <div class="flex w-full h-full justify-center items-center p-16">
    <People />   
    <!-- <Person msg="Hello Happy People" /> -->
  </div>  
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: whitesmoke;
  color: #2c3e50;
  padding-top: 12px;
}
</style>
