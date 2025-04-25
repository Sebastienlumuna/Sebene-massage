<script setup lang="ts">
const testimonials = [
  {
    name: 'Marie L.',
    text: 'Une expérience incroyablement relaxante. Sophie a su cibler parfaitement mes zones de tension. Je reviendrai sans hésiter !',
    rating: 5
  },
  {
    name: 'Thomas R.',
    text: 'Le massage deep tissue a complètement soulagé mes douleurs chroniques du dos. Service professionnel dans un cadre apaisant.',
    rating: 5
  },
  {
    name: 'Julie M.',
    text: 'Cadre magnifique et ambiance sereine. Le massage aux pierres chaudes était exactement ce dont j\'avais besoin après une semaine stressante.',
    rating: 4
  }
];
</script>

<template>
  <section class="section gradient-bg text-white">
    <div class="container mx-auto">
      <!-- Section Header -->
      <div class="text-center max-w-3xl mx-auto mb-16 animate-fade-in">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-6">Témoignages</h2>
        <div class="h-1 w-20 bg-white mx-auto mb-6"></div>
        <p class="text-gray-100">
          Découvrez ce que nos clients disent de leur expérience chez Harmonie Massage.
        </p>
      </div>
      
      <!-- Testimonials Grid -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div 
          v-for="(testimonial, index) in testimonials"
          :key="index"
          class="bg-white rounded-xl p-6 shadow-md text-gray-800 transform transition-all duration-300 hover:shadow-xl hover:-translate-y-2"
          :class="{ 'animate-slide-up': true }"
          :style="{ animationDelay: `${index * 0.1}s` }"
        >
          <!-- Quote Icon -->
          <div class="mb-4 text-primary">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 opacity-50" fill="currentColor" viewBox="0 0 24 24">
              <path d="M14.017 21v-7.391c0-5.704 3.731-9.57 8.983-10.609l.995 2.151c-2.432.917-3.995 3.638-3.995 5.849h4v10h-9.983zm-14.017 0v-7.391c0-5.704 3.748-9.57 9-10.609l.996 2.151c-2.433.917-3.996 3.638-3.996 5.849h3.983v10h-9.983z" />
            </svg>
          </div>
          
          <!-- Testimonial Text -->
          <p class="text-gray-700 mb-4">{{ testimonial.text }}</p>
          
          <!-- Rating -->
          <div class="flex mb-4">
            <svg 
              v-for="star in 5" 
              :key="star"
              xmlns="http://www.w3.org/2000/svg" 
              class="h-5 w-5" 
              :class="star <= testimonial.rating ? 'text-yellow-500' : 'text-gray-300'"
              viewBox="0 0 20 20" 
              fill="currentColor"
            >
              <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
            </svg>
          </div>
          
          <!-- Client Name -->
          <p class="font-semibold text-primary">{{ testimonial.name }}</p>
        </div>
      </div>
    </div>
  </section>
</template>