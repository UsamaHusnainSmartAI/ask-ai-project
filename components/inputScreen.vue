<template>

<div class="flex items-center space-x-3">
                <div class="bg-white rounded-full p-3">
                    <img src="../assets/icons/wechat.png" />
           
                </div>
    </div>
    <div class="text-container">         
                    <span class="flex flex-row pt-3">
                        
    <p class="text-effect">How Can I Help You Today?</p>

       
    </span>
</div>
    <div class="flex items-start lg:w-2/3 w-full pt-10">
    <div class="bg-white p-2 rounded-full mx-3">
      <svg width="24" height="25" viewBox="0 0 24 25" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M20.0306 16.0306C19.961 16.1003 19.8782 16.1557 19.7872 16.1934C19.6961 16.2311 19.5986 16.2506 19.5 16.2506C19.4014 16.2506 19.3038 16.2311 19.2128 16.1934C19.1217 16.1557 19.039 16.1003 18.9694 16.0306L12 9.06029L5.03061 16.0306C4.88988 16.1713 4.69901 16.2504 4.49999 16.2504C4.30097 16.2504 4.1101 16.1713 3.96936 16.0306C3.82863 15.8899 3.74957 15.699 3.74957 15.5C3.74957 15.301 3.82863 15.1101 3.96936 14.9694L11.4694 7.46935C11.539 7.39962 11.6217 7.3443 11.7128 7.30656C11.8038 7.26882 11.9014 7.24939 12 7.24939C12.0986 7.24939 12.1961 7.26882 12.2872 7.30656C12.3782 7.3443 12.461 7.39962 12.5306 7.46935L20.0306 14.9694C20.1003 15.039 20.1557 15.1217 20.1934 15.2128C20.2312 15.3038 20.2506 15.4014 20.2506 15.5C20.2506 15.5985 20.2312 15.6961 20.1934 15.7872C20.1557 15.8782 20.1003 15.9609 20.0306 16.0306Z" fill="#1F2022"/>
      </svg>
    </div>

    <div class="flex-1">
      <form class="flex items-center w-full">   
        <div class="relative w-full" @dblclick="emitToggle">
          <div v-if="!isVoiceOpen" class="absolute  left-3 top-1/2 -translate-y-1/2 z-10">
            <button 
              @click.prevent="openVoiceDialog" 
              class="p-3 bg-white rounded-full hover:bg-gray-200 transition-colors"
            >
              <svg width="24" height="25" viewBox="0 0 24 25" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 17C13.1931 16.9988 14.337 16.5243 15.1806 15.6806C16.0243 14.837 16.4988 13.6931 16.5 12.5V6.5C16.5 5.30653 16.0259 4.16193 15.182 3.31802C14.3381 2.47411 13.1935 2 12 2C10.8065 2 9.66193 2.47411 8.81802 3.31802C7.97411 4.16193 7.5 5.30653 7.5 6.5V12.5C7.50124 13.6931 7.97575 14.837 8.81939 15.6806C9.66303 16.5243 10.8069 16.9988 12 17ZM9 6.5C9 5.70435 9.31607 4.94129 9.87868 4.37868C10.4413 3.81607 11.2044 3.5 12 3.5C12.7956 3.5 13.5587 3.81607 14.1213 4.37868C14.6839 4.94129 15 5.70435 15 6.5V12.5C15 13.2956 14.6839 14.0587 14.1213 14.6213C13.5587 15.1839 12.7956 15.5 12 15.5C11.2044 15.5 10.4413 15.1839 9.87868 14.6213C9.31607 14.0587 9 13.2956 9 12.5V6.5ZM12.75 19.9625V23C12.75 23.1989 12.671 23.3897 12.5303 23.5303C12.3897 23.671 12.1989 23.75 12 23.75C11.8011 23.75 11.6103 23.671 11.4697 23.5303C11.329 23.3897 11.25 23.1989 11.25 23V19.9625C9.40091 19.7743 7.68728 18.9072 6.44048 17.5288C5.19368 16.1504 4.50228 14.3586 4.5 12.5C4.5 12.3011 4.57902 12.1103 4.71967 11.9697C4.86032 11.829 5.05109 11.75 5.25 11.75C5.44891 11.75 5.63968 11.829 5.78033 11.9697C5.92098 12.1103 6 12.3011 6 12.5C6 14.0913 6.63214 15.6174 7.75736 16.7426C8.88258 17.8679 10.4087 18.5 12 18.5C13.5913 18.5 15.1174 17.8679 16.2426 16.7426C17.3679 15.6174 18 14.0913 18 12.5C18 12.3011 18.079 12.1103 18.2197 11.9697C18.3603 11.829 18.5511 11.75 18.75 11.75C18.9489 11.75 19.1397 11.829 19.2803 11.9697C19.421 12.1103 19.5 12.3011 19.5 12.5C19.4977 14.3586 18.8063 16.1504 17.5595 17.5288C16.3127 18.9072 14.5991 19.7743 12.75 19.9625Z" fill="#5B626B"/>
              </svg>
            </button>
          </div>

          <input 
            type="text" 
            v-model="question" 
            @keyup.enter="emitToggle"
            id="simple-search" 
            class="h-20 bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-xl focus:ring-blue-500 focus:border-blue-500 block w-full pl-20 pr-4 py-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" 
            placeholder="Input Command" 
            required 
          />
        </div>
      </form>

      <VoiceDialogue 
        v-if="isVoiceOpen" 
        :isOpen="isVoiceOpen" 
        :imageSrc="voiceImage"
        @close="closeVoiceDialog"
      />
    </div>
  </div>
            
            <div class="text-xs sm:text-sm py-2 ">
                <p class="text-gray-400">AskAIs can make mistakes. Check important info.</p>
            </div>
            <div v-show="question" class="w-5/6 p-2 mt-20 hidden sm:block bg-white border border-gray-200 rounded-lg shadow-sm dark:bg-gray-800 dark:border-gray-700">
                <div class="h-auto grid grid-cols-12">
                    <div class="col-span-4 p-3 h-72 overflow-y-auto [-ms-overflow-style:'none'] [scrollbar-width:'none'] [&::-webkit-scrollbar]:hidden">
                        <h5 class="mb-2 text-md font-bold tracking-tight text-gray-900 dark:text-white">Suggest for you</h5>
                        <a href="#">
                            <div class="text-md my-3 px-2 border-l-2 border-gray-300">
                                <p class="mb-1 font-semibold text-gray-500 dark:text-gray-400">Button styling with React</p>
                                <p class="mb-1 text-sm font-normal text-gray-500 dark:text-gray-400">Short description for the suggested content</p>
                            </div>
                        </a>
                        <a href="#">
                            <div class="text-md my-3 px-2 border-l-2 border-gray-300">
                                <p class="mb-1 font-semibold text-gray-500 dark:text-gray-400">Button styling with React</p>
                                <p class="mb-1 text-sm font-normal text-gray-500 dark:text-gray-400">Short description for the suggested content</p>
                            </div>
                        </a>
                        <a href="#">
                            <div class="text-md my-3 px-2 border-l-2 border-gray-300">
                                <p class="mb-1 font-semibold text-gray-500 dark:text-gray-400">Button styling with React</p>
                                <p class="mb-1 text-sm font-normal text-gray-500 dark:text-gray-400">Short description for the suggested content</p>
                            </div>
                        </a>
                        <a href="#">
                            <div class="text-md my-3 px-2 border-l-2 border-gray-300">
                                <p class="mb-1 font-semibold text-gray-500 dark:text-gray-400">Button styling with React</p>
                                <p class="mb-1 text-sm font-normal text-gray-500 dark:text-gray-400">Short description for the suggested content</p>
                            </div>
                        </a>
                        <a href="#">
                            <div class="text-md my-3 px-2 border-l-2 border-gray-300">
                                <p class="mb-1 font-semibold text-gray-500 dark:text-gray-400">Button styling with React</p>
                                <p class="mb-1 text-sm font-normal text-gray-500 dark:text-gray-400">Short description for the suggested content</p>
                            </div>
                        </a>

                    </div>

                    <div class="p-4 col-span-8">
                        <h5 class="mb-2 text-md font-bold tracking-tight text-gray-900 dark:text-white">Images</h5>
                        
                        <div class="w-4/5 overflow-x-auto whitespace-nowrap">
                            <div class="flex space-x-3 py-3">
                                <img class="h-20 w-40 rounded-lg" src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" alt="">
                            
                                <img class="h-20 w-30 rounded-lg" src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" alt="">
                                
                                <img class="h-20 w-30 rounded-lg" src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" alt="">
                            
                                <img class="h-20 w-30 rounded-lg" src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" alt="">
                                
                                <img class="h-20 w-30 rounded-lg" src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" alt="">
                            
                                <img class="h-20 w-30 rounded-lg" src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" alt="">
                                
                                <img class="h-20 w-30 rounded-lg" src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" alt="">
                            
                                <img class="h-20 w-30 rounded-lg" src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" alt="">
                                
                                <img class="h-20 w-30 rounded-lg" src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" alt="">
                            
                                <img class="h-20 w-30 rounded-lg" src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" alt="">
                                
                                <img class="h-20 w-30 rounded-lg" src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" alt="">
                            
                                <img class="h-20 w-30 rounded-lg" src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" alt="">
                                
                            </div>
                        </div>

                        <h5 class="my-2 text-md font-bold tracking-tight text-gray-900 dark:text-white">Videos</h5>
                        <div class="w-full overflow-x-auto whitespace-nowrap">
                            <div class="flex space-x-3 py-3">
                                <div class="h-20 w-40">
                                    <img src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" class="w-full h-full object-cover rounded-lg">
                                </div>
                                <div class="h-20 w-40">
                                    <img src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" class="w-full h-full object-cover rounded-lg">
                                </div>
                                <div class="h-20 w-40">
                                    <img src="https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image.jpg" class="w-full h-full object-cover rounded-lg">
                                </div>
                                
                                
                            </div>
                        </div>


                    </div>
                </div>
                
            </div>
</template>


<script lang="ts" setup>
const question = ref('');
import { ref, defineEmits } from 'vue';
import VoiceDialogue from '../components/VoiceDialogue.vue'
import voiceImage from '../assets/images/voice.png' ;
import Logo from '../components/Logo.vue';


const isVoiceOpen = ref(false)

const openVoiceDialog = () => {
  isVoiceOpen.value = true
}

const closeVoiceDialog = () => {
  isVoiceOpen.value = false
}

const emit = defineEmits(['toggleComponent'])

const emitToggle = () => {
    emit('toggleComponent')
}

</script>
