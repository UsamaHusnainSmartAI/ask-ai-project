<script setup>
import { onMounted } from 'vue'
import { useFlowbite } from '~/composables/useFlowbite';
import { 
    initAccordions, 
    initCarousels, 
    initCollapses, 
    initDials, 
    initDismisses, 
    initDrawers, 
    initDropdowns, 
    initModals, 
    initPopovers, 
    initTabs, 
    initTooltips } from 'flowbite'

// initialize components based on data attribute selectors
onMounted(() => {
    useFlowbite(() => {
        initAccordions();
        initCarousels();
        initCollapses();
        initDials();
        initDismisses();
        initDrawers();
        initDropdowns();
        initModals();
        initPopovers();
        initTabs();
        initTooltips();
    })
})
</script>

<template class="bg-gray-100 ">

  
        <Navigation />
        
        <Sidebar />
            
        <!-- Content -->
        <main class="p-6 flex-1 h-screen overflow-y-auto bg-gray-100">
            <NuxtPage />
        </main>
        
</template>