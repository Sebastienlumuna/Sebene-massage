<script setup lang="ts">
defineProps<{
  id: string;
}>();
</script>

<template>
  <section :id="id" class="section bg-accent">
    <div class="container mx-auto">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
        <!-- Image Column -->
        <div class="md:order-2 animate-slide-in">
          <div class="relative">
            <div class="absolute -top-4 -left-4 w-full h-full bg-primary rounded-xl"></div>
            <img 
              src="https://images.pexels.com/photos/5793990/pexels-photo-5793990.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2" 
              alt="Portrait du propriétaire" 
              class="w-full h-auto rounded-xl relative z-10 shadow-lg"
            />
          </div>
        </div>
        
        <!-- Content Column -->
        <div class="md:order-1 animate-slide-up">
          <h2 class="text-3xl md:text-4xl font-bold mb-6">À Propos</h2>
          <div class="h-1 w-20 bg-gradient-to-r from-primary to-secondary mb-6"></div>
          
          <h3 class="text-xl md:text-2xl font-semibold text-primary-dark mb-4">
            Sebastien Lumuna, Fondateur & Masseur professionnel
          </h3>
          
          <p class="text-gray-700 mb-4">
            Bienvenue chez Sebene Massage. Je suis Sebastien, passionné par l'art du massage depuis plus de 10 ans. Formé aux techniques traditionnelles et modernes, j'ai créé ce lieu pour offrir une expérience unique de détente et de bien-être.
          </p>
          
          <p class="text-gray-700 mb-6">
            Mon approche combine expertise technique et écoute attentive. Chaque séance est personnalisée selon vos besoins spécifiques, pour vous procurer un moment d'évasion totale dans un cadre intime et apaisant.
          </p>
          
          <div class="grid grid-cols-2 gap-4 mb-6">
            <div class="flex items-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-primary mr-2" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
              </svg>
              <span>10+ ans d'expérience</span>
            </div>
            <div class="flex items-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-primary mr-2" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
              </svg>
              <span>Certification professionnelle</span>
            </div>
            <div class="flex items-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-primary mr-2" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
              </svg>
              <span>Approche personnalisée</span>
            </div>
            <div class="flex items-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-primary mr-2" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
              </svg>
              <span>Cadre privé et relaxant</span>
            </div>
          </div>
          
          <a href="#contact" class="btn btn-primary">
            Réserver une séance
          </a>
        </div>
      </div>
    </div>
  </section>
</template>