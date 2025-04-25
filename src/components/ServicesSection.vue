<script setup lang="ts">
defineProps<{
  id: string;
}>();

const services = [
  {
    title: 'Massage Suédois',
    description: 'Un massage classique qui détend les muscles et améliore la circulation sanguine avec des mouvements longs et fluides.',
    duration: '60 min',
    image: 'https://images.pexels.com/photos/5240677/pexels-photo-5240677.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
  },
  {
    title: 'Massage Deep Tissue',
    description: 'Technique profonde ciblant les nœuds musculaires et les tensions chroniques pour un soulagement intense.',
    duration: '75 min',
    image: 'https://images.pexels.com/photos/3757952/pexels-photo-3757952.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
  },
  {
    title: 'Massage aux Pierres Chaudes',
    description: 'Combinaison de massage manuel et de pierres volcaniques chaudes pour une relaxation profonde.',
    duration: '90 min',
    image: 'https://images.pexels.com/photos/3865560/pexels-photo-3865560.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
  },
  {
    title: 'Réflexologie Plantaire',
    description: 'Stimulation des points de pression des pieds pour équilibrer l\'énergie du corps et favoriser la guérison naturelle.',
    duration: '45 min',
    image: 'https://images.pexels.com/photos/4498376/pexels-photo-4498376.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
  }
];
</script>

<template>
  <section :id="id" class="section">
    <div class="container mx-auto">
      <!-- Section Header -->
      <div class="text-center max-w-3xl mx-auto mb-16 animate-fade-in">
        <h2 class="text-3xl md:text-4xl font-bold mb-6">Nos Services</h2>
        <div class="h-1 w-20 bg-gradient-to-r from-primary to-secondary mx-auto mb-6"></div>
        <p class="text-gray-700">
          Découvrez notre gamme de massages thérapeutiques, conçus pour répondre à vos besoins spécifiques et vous offrir un moment de pure détente.
        </p>
      </div>
      
      <!-- Services Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div 
          v-for="(service, index) in services" 
          :key="index"
          class="card group hover:translate-y-[-5px] animate-slide-up"
          :style="{ animationDelay: `${index * 0.1}s` }"
        >
          <div class="relative h-64 overflow-hidden">
            <img 
              :src="service.image" 
              :alt="service.title"
              class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-primary to-transparent opacity-30"></div>
            <div class="absolute bottom-4 left-4 px-3 py-1 bg-primary text-white rounded-full text-sm">
              {{ service.duration }}
            </div>
          </div>
          <div class="p-6">
            <h3 class="text-xl font-semibold mb-3">{{ service.title }}</h3>
            <p class="text-gray-700 mb-4">{{ service.description }}</p>
            <a 
              href="#contact" 
              class="inline-flex items-center text-primary font-medium hover:text-secondary transition-colors duration-300"
            >
              Réserver
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-1" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
              </svg>
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>