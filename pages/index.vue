import { Style } from "#components"

<script lang="ts" setup>

import { ref } from 'vue'
import inputScreen from '~/components/inputScreen.vue';
import outputScreen from '~/components/outputScreen.vue';

const showInputScreen = ref(true) // Control which component to show

const toggleComponent = () => {
    showInputScreen.value = !showInputScreen.value
}



</script>

<template>
    
    
     <div class="p-4 sm:ml-64">
        <div class="h-screen  items-center flex flex-col justify-center"> 
            
            <inputScreen v-if="showInputScreen" @toggleComponent="toggleComponent" />
            <outputScreen v-else />

          


        </div>
    </div> 
  </template>



<style>
  @media (max-width: 639px) {
    .custom-height {
      height: 3.5rem; 
    }
  }

  img {
    max-width: unset !important;
}
@keyframes textAppear {
        0% {
            width: 0;
        }
        100% {
            width: 100%;
        }
    }

    .text-effect {
        display: inline-block;
        overflow: hidden;
        white-space: nowrap;
        width: 0;
        animation: textAppear 2s steps(500) forwards;
        font-size: 1.5rem;
        font-weight: 600;
        color: #000000;
    }

    .group:hover {
        border-image: linear-gradient(to right, #D9F27E, #4ade80) 1;
    }

    .group:hover span {
        background-color: transparent;
    }
</style>