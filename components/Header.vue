<template>
      <header class="flex items-center justify-between p-4 text-white">
        <h1 class="text-3xl font-bold">My App</h1>
        <div class="md:hidden">
          <button @click="toggleMenu" class="focus:outline-none">
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
            </svg>
          </button>
        </div>
        <nav class="hidden md:flex space-x-4">
          <nuxt-link to="/" class="hover:underline">Home</nuxt-link>
          <nuxt-link to="/about" class="hover:underline">About</nuxt-link>
          <nuxt-link to="/contact" class="hover:underline">Contact</nuxt-link>
        </nav>
      </header>
    </template>

    <script>
    export default {
      methods: {
        toggleMenu() {
          this.$emit('toggle-menu');
        }
      }
    }
    </script>

    <style scoped>
    </style>
