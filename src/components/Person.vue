<script setup>
import { ref } from 'vue'
import { Icon } from '@iconify/vue'

const props = defineProps({
  person: Object
})
const person = props.person
const photoUrl = 'background-image: url(' + props.person.Photo + ');'

// console.log('log:', attention )
</script>

<template>
  <div class="min-w-[300px] w-auto h-[600px] bg-white flex flex-col rounded-xl shadow-xl shadow-gray-300/40">    
    <div class="image relative overflow-hidden h-[35%] bg-slate-200 bg-cover bg-center rounded-xl" :style="photoUrl">
      <div class="absolute top-2 right-0 flex flex-col gap-2 text-center ">
        <span v-if="person.Tags !== null" v-for="tag in person.Tags" :key="tag.Name" :style="'background-color:#' + tag.Color + ';'" class="block text-white font-bold px-2 rounded-xl translate-x-6 hover:translate-x-0 transition-all duration-100 cursor-pointer">
        {{ tag.Name }}
        </span>
      </div>
    </div>
    <div class="flex flex-col h-[65%] justify-between p-4"> 
      <div class="header">
        <h1 class="text-3xl font-bold leading-6 tracking-wide">{{ person.Name }}</h1>
        <h3 class="text-xl py-1 text-gray-500 tracking-wide">{{ person.Title }}</h3>
        <div class="w-full border-b-4 border-black mx-auto"></div>
      </div>
      <div class="profit">
        <div class="w-full flex justify-between items-center">
          <span>Profit</span>
          <span>+ ${{ person.Profit[0].Amount }}</span>
        </div>
        <div class="relative w-full h-4 bg-gray-200 rounded-xl overflow-hidden">
          <div class="relative h-4 rounded-xl overflow-hidden" :style="'background-color:#' + person.Profit[0].Color + ';width:'+ Math.round(person.Profit[0].Amount/10) + '%;'">        
        </div>
        </div>
      </div>

      <div class="attention">
        <div class="w-full flex justify-between items-center">
          <span>Attention</span>
          <span>48h</span>
        </div>
        <div v-if="person.Attention !== null" class="relative flex h-4 bg-yellow-200 rounded-xl overflow-hidden">
          <span v-for="attention in person.Attention" :key="person.Id" 
            class="block h-full rounded-r-xl -ml-2"
            :style="'width:' + attention.Amount + '%;background-color:#'+ attention.Color + ';'">
          </span> 
        </div>        
        <div v-else class="relative h-4 bg-yellow-200 rounded-xl overflow-hidden"></div>
      </div>

      <div class="params grid grid-cols-2 gap-2 h-[40%] p-4">

        <div class="relative w-full h-full flex items-center justify-end">
          <span class="px-2 z-10">15%</span>
          <div class="flex w-[40%] min-w-[1%] h-full bg-red-400 rounded-xl"></div>
        </div>

        <div class="relative w-full h-full flex items-center justify-start">          
          <div class="flex w-[20%] min-w-[1%] h-full bg-amber-400 rounded-xl"></div>
          <span class="px-2 z-10">12%</span>
        </div>

        <div class="relative w-full h-full flex items-center justify-end">
          <span class="pr-2">35%</span>
          <div class="flex w-[100%] min-w-[1%] h-full bg-blue-400 rounded-xl"></div>
        </div>

        <div class="relative w-full h-full flex items-center justify-end">          
          <div class="absolute flex w-[100%] min-w-[1%] h-full bg-green-400 rounded-xl"></div>
          <span class="px-2 z-10">38%</span>
        </div>

      </div>
    </div>
  </div>  
</template>

<style scoped>
</style>
