<script setup>
import { Icon } from '@iconify/vue'

</script>

<template>
  <header class="w-full h-12 flex justify-between items-center p-4">
    <div class="logo w-12 h-12">
      <img src="../assets/img/logo_demo.png" alt="logo">
    </div>

    <div class="sort flex items-center space-x-12 h-full">
      <div class="flex flex-nowrap space-x-4">
        <Icon class="w-6 h-6" icon="radix-icons:view-vertical" />
        <Icon class="w-6 h-6" icon="radix-icons:view-horizontal" />
        <Icon class="w-6 h-6" icon="radix-icons:view-grid" />
      </div>
      <div class="flex">
        <input class="rounded-xl px-4 border-2 border-gray-400" type="search" placeholder="search here">
      </div>
      <div class="flex flex-nowrap space-x-4">
        <span class="relative">
          <Icon class="w-6 h-6" icon="codicon:filter-filled" />
          <div class="absolute -top-1 -right-1 bg-red-500 badge badge-xs"></div>
        </span>
        
        <span class="relative">
          <Icon class="w-6 h-6" icon="fluent:arrow-sort-20-filled" />
          <div class="absolute -top-1 -right-1 bg-red-500 badge badge-xs"></div>
        </span>
      </div>        
    </div>
    <div class="ava w-12 h-12 bg-cover bg-center rounded-xl" style="background-image:url('../assets/img/face_byfNhh81CWU-unsplash.jpg');">
    </div>
  </header>
</template>
