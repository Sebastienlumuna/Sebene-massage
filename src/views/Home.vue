<script setup lang="ts">
import HeroSection from '../components/HeroSection.vue';
import AboutSection from '../components/AboutSection.vue';
import ServicesSection from '../components/ServicesSection.vue';
import TestimonialsSection from '../components/TestimonialsSection.vue';
import ContactSection from '../components/ContactSection.vue';
</script>

<template>
  <div class="home">
    <HeroSection id="accueil" />
    <AboutSection id="à-propos" />
    <ServicesSection id="services" />
    <TestimonialsSection />
    <ContactSection id="contact" />
  </div>
</template>