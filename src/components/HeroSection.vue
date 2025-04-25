<script setup lang="ts">
defineProps<{
  id: string;
}>();
</script>

<template>
  <section :id="id" class="relative h-screen flex items-center">
    <!-- Background Image with Overlay -->
    <div class="absolute inset-0 bg-cover bg-center" 
         style="background-image: url('https://images.pexels.com/photos/3757942/pexels-photo-3757942.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2');">
      <div class="absolute inset-0 bg-primary bg-opacity-50"></div>
    </div>
    
    <!-- Content -->
    <div class="container relative z-10 mx-auto px-4">
      <div class="max-w-3xl animate-fade-in">
        <h1 class="text-4xl md:text-6xl font-bold text-white mb-4">Sebene Massage</h1>
        <p class="text-xl md:text-2xl text-white mb-8">
          Découvrez l'art de la relaxation profonde et du bien-être.
        </p>
        <div class="flex flex-col sm:flex-row gap-4">
          <a href="#services" class="btn btn-primary">
            Nos services
          </a>
          <a href="#contact" class="btn btn-outline border-white text-white hover:bg-white hover:text-primary">
            Prendre rendez-vous
          </a>
        </div>
      </div>
    </div>
    
    <!-- Scroll Down Indicator -->
    <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-white animate-bounce">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
      </svg>
    </div>
  </section>
</template>