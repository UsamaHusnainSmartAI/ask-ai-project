<template>
    <teleport to="body">
      <div v-if="isOpen" class="fixed inset-0 flex items-center justify-center bg-gray-800 bg-opacity-50">
        <div class="bg-white w-[400px] rounded-xl p-6 relative">
          
          <!-- Close Button -->
          <button @click="closeModal" class="absolute top-4 right-4 text-gray-400 hover:text-black">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-5 h-5">
              <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
  
          <!-- Title -->
          <h2 class="text-center font-semibold text-lg">Voice Dialogue</h2>
          <hr class="mt-2 mb-4 border-gray-300" />
  
          <!-- Circular Image -->
          <div class="flex justify-center">
            <div class="w-32 h-32 rounded-full border-4 border-gray-200 flex items-center justify-center">
              <img :src="imageSrc" alt="Voice Image" class="w-28 h-28 rounded-full object-cover" />
            </div>
          </div>
  
          <!-- Icons Below Image -->
          <div class="flex justify-center space-x-6 mt-4">
            <!-- Mute Button -->
            <button class="p-2 bg-gray-100 rounded-full hover:bg-gray-200">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-5 h-5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 8.25v-1.5a3.75 3.75 0 10-7.5 0v1.5m-3 3V8.25a6.75 6.75 0 0113.5 0v3m-3 3.75v3m-6-3v3m9-6V12a9 9 0 10-18 0v3m9-3v3" />
              </svg>
            </button>
  
            <!-- Bookmark Button -->
            <button class="p-2 bg-gray-100 rounded-full hover:bg-gray-200">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-5 h-5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M5.25 3h13.5A2.25 2.25 0 0121 5.25v15.07a.75.75 0 01-1.175.625L12 16.3l-7.825 4.644A.75.75 0 013 20.32V5.25A2.25 2.25 0 015.25 3z" />
              </svg>
            </button>
          </div>
  
        </div>
      </div>
    </teleport>
  </template>
  
  <script setup>
  import { defineProps, defineEmits } from 'vue';
  
  defineProps({
    isOpen: Boolean, // Controls modal visibility
    imageSrc: String // Dynamic image source
  });
  
  const emit = defineEmits(['close']);
  
  const closeModal = () => {
    emit('close'); // Emit event to close modal
  };
  </script>
  