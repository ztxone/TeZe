<script setup>
import { Icon } from '@iconify/vue'

</script>

<template>
  <header class="w-full flex justify-between items-center p-4">
    <div class="logo w-12 h-12">
      <img src="../assets/img/logo_demo.png" alt="logo">
    </div>

    <div class="sort flex items-center space-x-4 md:space-x-12">
      <div class="flex flex-nowrap space-x-4">
        <Icon class="w-6 h-6 text-blue-500 cursor-pointer" icon="radix-icons:view-vertical" />
        <Icon class="w-6 h-6 hover:text-blue-500 cursor-pointer" icon="radix-icons:view-horizontal" />
        <Icon class="w-6 h-6 hover:text-blue-500 cursor-pointer" icon="radix-icons:view-grid" />
      </div>
      <div class="flex">
        <Icon class="md:hidden w-6 h-6 hover:text-blue-500 cursor-pointer" icon="bx:bx-search-alt-2" />

        <input class="hidden md:inline rounded-xl px-4 border-2 border-gray-400" type="search" placeholder="search here">
      </div>
      <div class="flex flex-nowrap space-x-4">
        <span class="relative">
          <Icon class="w-6 h-6 hover:text-blue-500 cursor-pointer" icon="codicon:filter-filled" />
          <div class="absolute -top-1 -right-1  w-3 h-3 rounded-full bg-red-500"></div>
        </span>
        
        <span class="relative">
          <Icon class="w-6 h-6 hover:text-blue-500 cursor-pointer" icon="fluent:arrow-sort-20-filled" />
          <div class="absolute -top-1 -right-1 w-3 h-3 rounded-full bg-red-500"></div>
        </span>
      </div>        
    </div>
    <div class="ava w-12 h-12 bg-cover bg-center rounded-xl" style="background-image:url('../assets/img/face_byfNhh81CWU-unsplash.jpg');">
    </div>
  </header>
</template>
