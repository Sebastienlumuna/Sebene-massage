<script setup lang="ts">
import { ref, onMounted, onUnmounted, computed } from 'vue';

const isMenuOpen = ref(false);
const scrollPosition = ref(0);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const updateScroll = () => {
  scrollPosition.value = window.scrollY;
};

const navbarClasses = computed(() => {
  return {
    'bg-white shadow-md': scrollPosition.value > 50,
    'bg-transparent': scrollPosition.value <= 50
  };
});

const textClasses = computed(() => {
  return {
    'text-white': scrollPosition.value <= 50,
    'text-primary': scrollPosition.value > 50
  };
});

onMounted(() => {
  window.addEventListener('scroll', updateScroll);
  updateScroll();
});

onUnmounted(() => {
  window.removeEventListener('scroll', updateScroll);
});
</script>

<template>
  <header 
    class="fixed top-0 left-0 w-full z-50 transition-all duration-300" 
    :class="navbarClasses"
  >
    <div class="container mx-auto px-4 py-4">
      <div class="flex justify-between items-center">
        <!-- Logo -->
        <a href="#" class="text-2xl font-bold transition-colors duration-300" :class="textClasses">
          Harmonie Massage
        </a>
        
        <!-- Desktop Menu -->
        <nav class="hidden md:flex space-x-8">
          <a 
            v-for="(item, index) in ['Accueil', 'À propos', 'Services', 'Contact']" 
            :key="index"
            :href="`#${item.toLowerCase().replace(' ', '-')}`"
            class="transition-colors duration-300 hover:text-secondary-light"
            :class="textClasses"
          >
            {{ item }}
          </a>
        </nav>
        
        <!-- Mobile Menu Button -->
        <button 
          class="md:hidden focus:outline-none transition-colors duration-300"
          :class="textClasses"
          @click="toggleMenu"
        >
          <svg 
            xmlns="http://www.w3.org/2000/svg" 
            class="h-6 w-6" 
            fill="none" 
            viewBox="0 0 24 24" 
            stroke="currentColor"
          >
            <path 
              v-if="!isMenuOpen" 
              stroke-linecap="round" 
              stroke-linejoin="round" 
              stroke-width="2" 
              d="M4 6h16M4 12h16M4 18h16"
            />
            <path 
              v-else 
              stroke-linecap="round" 
              stroke-linejoin="round" 
              stroke-width="2" 
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>
      
      <!-- Mobile Menu -->
      <div 
        v-if="isMenuOpen" 
        class="md:hidden mt-4 py-2 rounded-lg bg-white shadow-lg animate-fade-in"
      >
        <div class="flex flex-col">
          <a 
            v-for="(item, index) in ['Accueil', 'À propos', 'Services', 'Contact']" 
            :key="index"
            :href="`#${item.toLowerCase().replace(' ', '-')}`"
            class="py-2 px-4 text-primary hover:bg-accent transition-colors duration-200"
            @click="isMenuOpen = false"
          >
            {{ item }}
          </a>
        </div>
      </div>
    </div>
  </header>
</template>