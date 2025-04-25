<script setup lang="ts">
import { ref } from 'vue';

defineProps<{
  id: string;
}>();

const form = ref({
  firstName: '',
  lastName: '',
  email: '',
  phone: '',
  message: '',
  service: ''
});

const errors = ref({
  firstName: '',
  lastName: '',
  email: '',
  phone: '',
  message: '',
  service: ''
});

const isSubmitted = ref(false);
const isSubmitting = ref(false);

const validateForm = () => {
  let isValid = true;
  errors.value = {
    firstName: '',
    lastName: '',
    email: '',
    phone: '',
    message: '',
    service: ''
  };

  if (!form.value.firstName) {
    errors.value.firstName = 'Le prénom est requis';
    isValid = false;
  }

  if (!form.value.lastName) {
    errors.value.lastName = 'Le nom est requis';
    isValid = false;
  }

  if (!form.value.email) {
    errors.value.email = 'L\'email est requis';
    isValid = false;
  } else if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(form.value.email)) {
    errors.value.email = 'Veuillez entrer un email valide';
    isValid = false;
  }

  if (!form.value.phone) {
    errors.value.phone = 'Le téléphone est requis';
    isValid = false;
  }

  if (!form.value.service) {
    errors.value.service = 'Veuillez sélectionner un service';
    isValid = false;
  }

  return isValid;
};

const submitForm = async () => {
  if (!validateForm()) return;
  
  isSubmitting.value = true;
  
  // Simulating API call - this will be replaced with Firebase Firestore
  await new Promise(resolve => setTimeout(resolve, 1000));
  
  isSubmitting.value = false;
  isSubmitted.value = true;
  
  // Reset form
  form.value = {
    firstName: '',
    lastName: '',
    email: '',
    phone: '',
    message: '',
    service: ''
  };
  
  // Structure for Firestore implementation
  // This code will be uncommented and modified when Firebase is integrated
  /*
  try {
    const db = getFirestore();
    const bookingsCollection = collection(db, 'bookings');
    await addDoc(bookingsCollection, {
      ...form.value,
      createdAt: new Date()
    });
    isSubmitting.value = false;
    isSubmitted.value = true;
  } catch (error) {
    console.error('Error submitting form:', error);
    isSubmitting.value = false;
  }
  */
};
</script>

<template>
  <section :id="id" class="section bg-accent">
    <div class="container mx-auto">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
        <!-- Contact Information -->
        <div class="animate-slide-in">
          <h2 class="text-3xl md:text-4xl font-bold mb-6">Contactez-nous</h2>
          <div class="h-1 w-20 bg-gradient-to-r from-primary to-secondary mb-6"></div>
          
          <p class="text-gray-700 mb-8">
            Prêt à réserver votre massage? Remplissez le formulaire ci-contre ou contactez-nous directement. Nous répondrons à votre demande dans les plus brefs délais.
          </p>
          
          <div class="space-y-6 mb-8">
            <div class="flex items-start">
              <div class="bg-primary rounded-full p-3 mr-4">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
                </svg>
              </div>
              <div>
                <h3 class="text-lg font-semibold text-primary-dark mb-1">Adresse</h3>
                <p class="text-gray-700">123 Avenue de la Relaxation, 75001 Paris</p>
              </div>
            </div>
            
            <div class="flex items-start">
              <div class="bg-primary rounded-full p-3 mr-4">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                </svg>
              </div>
              <div>
                <h3 class="text-lg font-semibold text-primary-dark mb-1">Téléphone</h3>
                <p class="text-gray-700">+33 1 23 45 67 89</p>
              </div>
            </div>
            
            <div class="flex items-start">
              <div class="bg-primary rounded-full p-3 mr-4">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                </svg>
              </div>
              <div>
                <h3 class="text-lg font-semibold text-primary-dark mb-1">Email</h3>
                <p class="text-gray-700">contact@harmoniemassage.com</p>
              </div>
            </div>
            
            <div class="flex items-start">
              <div class="bg-primary rounded-full p-3 mr-4">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <div>
                <h3 class="text-lg font-semibold text-primary-dark mb-1">Horaires d'ouverture</h3>
                <p class="text-gray-700">Lundi - Vendredi: 9h00 - 19h00</p>
                <p class="text-gray-700">Samedi: 10h00 - 16h00</p>
              </div>
            </div>
          </div>
          
          <!-- Map or Additional Image -->
          <div class="rounded-xl overflow-hidden shadow-lg">
            <img 
              src="https://images.pexels.com/photos/3771110/pexels-photo-3771110.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2" 
              alt="Notre salon" 
              class="w-full h-auto"
            />
          </div>
        </div>
        
        <!-- Contact Form -->
        <div class="card p-8 animate-slide-up">
          <h3 class="text-2xl font-semibold text-primary-dark mb-6">Réservez une séance</h3>
          
          <!-- Success Message -->
          <div v-if="isSubmitted" class="bg-green-100 border border-green-400 text-green-700 px-4 py-3 rounded mb-6 animate-fade-in">
            <p>Merci ! Votre demande a été envoyée avec succès. Nous vous contacterons prochainement.</p>
          </div>
          
          <!-- Form -->
          <form v-else @submit.prevent="submitForm" class="space-y-4">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <!-- First Name -->
              <div>
                <label for="firstName" class="form-label">Prénom</label>
                <input 
                  id="firstName"
                  v-model="form.firstName"
                  type="text" 
                  class="form-input"
                  :class="{ 'border-red-500': errors.firstName }"
                />
                <p v-if="errors.firstName" class="form-error">{{ errors.firstName }}</p>
              </div>
              
              <!-- Last Name -->
              <div>
                <label for="lastName" class="form-label">Nom</label>
                <input 
                  id="lastName"
                  v-model="form.lastName"
                  type="text" 
                  class="form-input"
                  :class="{ 'border-red-500': errors.lastName }"
                />
                <p v-if="errors.lastName" class="form-error">{{ errors.lastName }}</p>
              </div>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <!-- Email -->
              <div>
                <label for="email" class="form-label">Email</label>
                <input 
                  id="email"
                  v-model="form.email"
                  type="email" 
                  class="form-input"
                  :class="{ 'border-red-500': errors.email }"
                />
                <p v-if="errors.email" class="form-error">{{ errors.email }}</p>
              </div>
              
              <!-- Phone -->
              <div>
                <label for="phone" class="form-label">Téléphone</label>
                <input 
                  id="phone"
                  v-model="form.phone"
                  type="tel" 
                  class="form-input"
                  :class="{ 'border-red-500': errors.phone }"
                />
                <p v-if="errors.phone" class="form-error">{{ errors.phone }}</p>
              </div>
            </div>
            
            <!-- Service -->
            <div>
              <label for="service" class="form-label">Service souhaité</label>
              <select 
                id="service"
                v-model="form.service"
                class="form-input"
                :class="{ 'border-red-500': errors.service }"
              >
                <option value="">Sélectionnez un service</option>
                <option value="massage-suedois">Massage Suédois</option>
                <option value="deep-tissue">Massage Deep Tissue</option>
                <option value="pierres-chaudes">Massage aux Pierres Chaudes</option>
                <option value="reflexologie">Réflexologie Plantaire</option>
              </select>
              <p v-if="errors.service" class="form-error">{{ errors.service }}</p>
            </div>
            
            <!-- Message -->
            <div>
              <label for="message" class="form-label">Message (facultatif)</label>
              <textarea 
                id="message"
                v-model="form.message"
                rows="4" 
                class="form-input"
              ></textarea>
            </div>
            
            <!-- Submit Button -->
            <button 
              type="submit" 
              class="btn btn-primary w-full"
              :disabled="isSubmitting"
            >
              <span v-if="isSubmitting">
                <svg class="animate-spin -ml-1 mr-3 h-5 w-5 text-white inline-block" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                  <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                  <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                </svg>
                Envoi en cours...
              </span>
              <span v-else>Envoyer ma demande</span>
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>