<template>
      <div class="flex flex-col h-screen bg-gradient-to-r from-indigo-600 to-purple-600">
        <Header @toggle-menu="toggleMenu" />
        <main class="flex-grow flex items-center justify-center text-center text-white">
          <NuxtPage />
        </main>
        <Footer />
        
        <transition name="slide-fade">
          <div v-if="isMenuOpen" class="absolute top-0 left-0 w-full h-full bg-gray-800 bg-opacity-90 flex flex-col items-center justify-center md:hidden">
            <nav class="flex flex-col space-y-4 text-white">
              <nuxt-link to="/" class="hover:underline text-lg">Home</nuxt-link>
              <nuxt-link to="/about" class="hover:underline text-lg">About</nuxt-link>
              <nuxt-link to="/contact" class="hover:underline text-lg">Contact</nuxt-link>
              <button @click="toggleMenu" class="mt-6 px-4 py-2 bg-white text-indigo-600 rounded-full">Close</button>
            </nav>
          </div>
        </transition>
      </div>
    </template>

    <script>
    import Header from '~/components/Header.vue';
    import Footer from '~/components/Footer.vue';

    export default {
      components: {
        Header,
        Footer
      },
      data() {
        return {
          isMenuOpen: false
        }
      },
      methods: {
        toggleMenu() {
          this.isMenuOpen = !this.isMenuOpen;
        }
      }
    }
    </script>

    <style scoped>
      @keyframes fade-in {
        0% {
          opacity: 0;
          transform: translateY(20px);
        }
        100% {
          opacity: 1;
          transform: translateY(0);
        }
      }
      .animate-fade-in {
        animation: fade-in 1s ease-in-out forwards;
      }
      .slide-fade-enter-active, .slide-fade-leave-active {
        transition: opacity 0.5s, transform 0.5s;
      }
      .slide-fade-enter, .slide-fade-leave-to {
        opacity: 0;
        transform: translateY(-20px);
      }
    </style>
