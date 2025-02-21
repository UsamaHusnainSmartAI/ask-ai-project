<!-- <template>
    <teleport to="body">
      <div v-if="isOpen" class="fixed inset-0 flex items-center justify-center bg-gray-800 bg-opacity-50">
        <div class="bg-white w-[400px] p-6 relative"> -->
          
          <!-- Close Button -->
          <!-- <button @click="closeModal" class="absolute top-4 right-4 text-gray-400 hover:text-black">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-5 h-5">
              <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button> -->
  
          <!-- Title -->
          <!-- <h2 class="text-center font-semibold text-lg">Voice Dialogue</h2>
          <hr class="mt-2 mb-4 border-gray-300" /> -->
  
          <!-- Circular Image -->
          <!-- <div class="flex justify-center">
            <div class="w-32 h-32 rounded-full border-4 border-gray-200 flex items-center justify-center">
              <img :src="imageSrc" alt="Voice Image" class="w-28 h-28 rounded-full object-cover" />
            </div>
          </div> -->
  
          <!-- Icons Below Image -->
          <!-- <div class="flex justify-center space-x-6 mt-4"> -->
            <!-- Mute Button -->
            <!-- <button class="p-2 bg-gray-100 rounded-full hover:bg-gray-200">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-5 h-5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 8.25v-1.5a3.75 3.75 0 10-7.5 0v1.5m-3 3V8.25a6.75 6.75 0 0113.5 0v3m-3 3.75v3m-6-3v3m9-6V12a9 9 0 10-18 0v3m9-3v3" />
              </svg>
            </button> -->
  
            <!-- Bookmark Button -->
            <!-- <button class="p-2 bg-gray-100 rounded-full hover:bg-gray-200">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-5 h-5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M5.25 3h13.5A2.25 2.25 0 0121 5.25v15.07a.75.75 0 01-1.175.625L12 16.3l-7.825 4.644A.75.75 0 013 20.32V5.25A2.25 2.25 0 015.25 3z" />
              </svg>
            </button>
          </div>
  
        </div>
      </div>
    </teleport>
  </template> -->
  
  <!-- <script setup>
  import { defineProps, defineEmits } from 'vue';
  
  defineProps({
    isOpen: Boolean, 
    imageSrc: String 
  });
  
  const emit = defineEmits(['close']);
  
  const closeModal = () => {
    emit('close'); 
  };
  </script> -->
  


  <template>
    <teleport to="body">
      <!-- Overlay with backdrop blur -->
      <div v-if="isOpen" class="fixed inset-0 z-50">
        <!-- Backdrop with blur -->
        <div class="absolute inset-0 bg-black/30 backdrop-blur-sm"></div>
        
        <!-- Dialog Content -->
        <div class="relative z-50 h-full flex items-center justify-center">
          <div class="bg-white w-[500px] h-[400px] rounded-xl shadow-lg p-6 relative">
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
            <div class="flex justify-center pt-10">
              <div class="w-50 h-50 rounded-full border-4 border-gray-200 flex items-center justify-center">
                <img :src="imageSrc" alt="Voice Image" class="w-40 h-40 rounded-full object-cover" />
              </div>
            </div>
  
            <!-- Icons Below Image -->
            <div class="flex justify-center space-x-10 pt-12">
              <!-- Mute Button -->
              <div class="w-[40px] h-[40px] p-2 border border-gray-100 rounded-xl tooltip">
              <button @click="toggleMic" class="transition-all duration-300 ease-in-out hover:bg-[#D9F27E] group rounded-full">
                <svg v-if="isMuted" width="24" height="25" viewBox="0 0 24 25" fill="none" xmlns="http://www.w3.org/2000/svg">
               <path d="M12 17C13.1931 16.9988 14.337 16.5243 15.1806 15.6806C16.0243 14.837 16.4988 13.6931 16.5 12.5V6.5C16.5 5.30653 16.0259 4.16193 15.182 3.31802C14.3381 2.47411 13.1935 2 12 2C10.8065 2 9.66193 2.47411 8.81802 3.31802C7.97411 4.16193 7.5 5.30653 7.5 6.5V12.5C7.50124 13.6931 7.97575 14.837 8.81939 15.6806C9.66303 16.5243 10.8069 16.9988 12 17ZM9 6.5C9 5.70435 9.31607 4.94129 9.87868 4.37868C10.4413 3.81607 11.2044 3.5 12 3.5C12.7956 3.5 13.5587 3.81607 14.1213 4.37868C14.6839 4.94129 15 5.70435 15 6.5V12.5C15 13.2956 14.6839 14.0587 14.1213 14.6213C13.5587 15.1839 12.7956 15.5 12 15.5C11.2044 15.5 10.4413 15.1839 9.87868 14.6213C9.31607 14.0587 9 13.2956 9 12.5V6.5ZM12.75 19.9625V23C12.75 23.1989 12.671 23.3897 12.5303 23.5303C12.3897 23.671 12.1989 23.75 12 23.75C11.8011 23.75 11.6103 23.671 11.4697 23.5303C11.329 23.3897 11.25 23.1989 11.25 23V19.9625C9.40091 19.7743 7.68728 18.9072 6.44048 17.5288C5.19368 16.1504 4.50228 14.3586 4.5 12.5C4.5 12.3011 4.57902 12.1103 4.71967 11.9697C4.86032 11.829 5.05109 11.75 5.25 11.75C5.44891 11.75 5.63968 11.829 5.78033 11.9697C5.92098 12.1103 6 12.3011 6 12.5C6 14.0913 6.63214 15.6174 7.75736 16.7426C8.88258 17.8679 10.4087 18.5 12 18.5C13.5913 18.5 15.1174 17.8679 16.2426 16.7426C17.3679 15.6174 18 14.0913 18 12.5C18 12.3011 18.079 12.1103 18.2197 11.9697C18.3603 11.829 18.5511 11.75 18.75 11.75C18.9489 11.75 19.1397 11.829 19.2803 11.9697C19.421 12.1103 19.5 12.3011 19.5 12.5C19.4977 14.3586 18.8063 16.1504 17.5595 17.5288C16.3127 18.9072 14.5991 19.7743 12.75 19.9625Z" fill="#5B626B"/>
                  </svg>

                <svg v-else width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M20.0548 20.4956L5.05481 3.99564C4.92034 3.85119 4.73435 3.76557 4.53717 3.75733C4.33999 3.74909 4.1475 3.8189 4.00145 3.95163C3.8554 4.08436 3.76755 4.26931 3.75694 4.46638C3.74634 4.66345 3.81384 4.85676 3.94481 5.00439L7.49981 8.91471V12C7.49963 12.764 7.69397 13.5155 8.0645 14.1836C8.43504 14.8517 8.96958 15.4145 9.61775 15.8189C10.2659 16.2233 11.0064 16.456 11.7694 16.4952C12.5324 16.5343 13.2927 16.3785 13.9789 16.0425L15.0195 17.1863C14.1036 17.7222 13.061 18.0031 11.9998 18C10.409 17.9983 8.88393 17.3656 7.75909 16.2407C6.63425 15.1159 6.00155 13.5908 5.99981 12C5.99981 11.8011 5.92079 11.6103 5.78014 11.4697C5.63949 11.329 5.44872 11.25 5.24981 11.25C5.0509 11.25 4.86013 11.329 4.71948 11.4697C4.57883 11.6103 4.49981 11.8011 4.49981 12C4.5021 13.8587 5.19349 15.6504 6.44029 17.0288C7.68709 18.4072 9.40073 19.2744 11.2498 19.4625V22.5C11.2498 22.6989 11.3288 22.8897 11.4695 23.0303C11.6101 23.171 11.8009 23.25 11.9998 23.25C12.1987 23.25 12.3895 23.171 12.5301 23.0303C12.6708 22.8897 12.7498 22.6989 12.7498 22.5V19.4616C13.9243 19.3483 15.0545 18.9555 16.0461 18.316L18.9448 21.5035C19.0107 21.5777 19.0906 21.6381 19.18 21.6813C19.2694 21.7244 19.3665 21.7493 19.4656 21.7547C19.5647 21.76 19.6639 21.7456 19.7574 21.7123C19.8509 21.679 19.9368 21.6275 20.0103 21.5608C20.0837 21.494 20.1432 21.4134 20.1852 21.3235C20.2273 21.2336 20.2511 21.1362 20.2552 21.037C20.2593 20.9379 20.2438 20.8389 20.2094 20.7458C20.175 20.6527 20.1224 20.5674 20.0548 20.4947V20.4956ZM11.9998 15C11.2042 15 10.4411 14.6839 9.87849 14.1213C9.31588 13.5587 8.99981 12.7957 8.99981 12V10.5647L12.9054 14.8603C12.6125 14.953 12.3071 15.0001 11.9998 15ZM17.3923 14.6335C17.7946 13.814 18.0025 12.9129 17.9998 12C17.9998 11.8011 18.0788 11.6103 18.2195 11.4697C18.3601 11.329 18.5509 11.25 18.7498 11.25C18.9487 11.25 19.1395 11.329 19.2801 11.4697C19.4208 11.6103 19.4998 11.8011 19.4998 12C19.5029 13.1414 19.2428 14.2681 18.7395 15.2925C18.6779 15.4188 18.582 15.5252 18.4628 15.5996C18.3436 15.674 18.2059 15.7135 18.0654 15.7135C17.9513 15.7136 17.8386 15.6873 17.7364 15.6366C17.5577 15.5492 17.4212 15.3944 17.3566 15.2063C17.2921 15.0181 17.3049 14.8121 17.3923 14.6335ZM7.87481 4.20658C8.28787 3.25916 9.01447 2.4828 9.9325 2.00799C10.8505 1.53317 11.904 1.38884 12.9159 1.59925C13.9278 1.80966 14.8365 2.36199 15.4891 3.1634C16.1418 3.96482 16.4987 4.96647 16.4998 6.00002V12C16.4997 12.1566 16.4915 12.313 16.4754 12.4688C16.4561 12.6539 16.3687 12.8252 16.23 12.9495C16.0914 13.0737 15.9116 13.142 15.7254 13.141C15.6992 13.1423 15.6729 13.1423 15.6467 13.141C15.4489 13.1202 15.2675 13.0217 15.1423 12.8671C15.0171 12.7126 14.9585 12.5147 14.9792 12.3169C14.9895 12.2138 14.9951 12.1069 14.9951 12.0019V6.00002C14.9931 5.31191 14.7547 4.64539 14.3197 4.11221C13.8847 3.57902 13.2796 3.21158 12.6059 3.07148C11.9322 2.93138 11.2309 3.02713 10.6194 3.34269C10.0079 3.65825 9.52346 4.17443 9.24731 4.80471C9.21226 4.90089 9.15788 4.98888 9.08753 5.06325C9.01719 5.13762 8.93236 5.19681 8.83828 5.23716C8.74419 5.27751 8.64285 5.29817 8.54047 5.29788C8.4381 5.29758 8.33688 5.27632 8.24303 5.23543C8.14918 5.19453 8.0647 5.13485 7.99479 5.06007C7.92488 4.98529 7.87101 4.89698 7.83652 4.8006C7.80202 4.70422 7.78762 4.60179 7.79421 4.49963C7.8008 4.39747 7.82823 4.29774 7.87481 4.20658Z" fill="#1F2022"/>
                </svg>

              </button>
              <span class="tooltiptext text-xs bg-white rounded-xl mb-1 shadow-sm"></span>
            </div>
  
              <!-- Bookmark Button -->
               <div class="w-[40px] h-[40px] p-2 border border-gray-100 rounded-xl tooltip">
              <button class=" transition-all duration-300 ease-in-out hover:bg-[#D9F27E] group rounded-full">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
               <path d="M17.25 3H6.75C6.35218 3 5.97064 3.15804 5.68934 3.43934C5.40804 3.72064 5.25 4.10218 5.25 4.5V21C5.25007 21.1338 5.28595 21.2652 5.35393 21.3805C5.42191 21.4958 5.5195 21.5908 5.63659 21.6557C5.75367 21.7206 5.88598 21.7529 6.01978 21.7494C6.15358 21.7458 6.284 21.7066 6.3975 21.6356L12 18.1341L17.6034 21.6356C17.7169 21.7063 17.8472 21.7454 17.9809 21.7488C18.1146 21.7522 18.2467 21.7198 18.3636 21.655C18.4806 21.5902 18.5781 21.4953 18.646 21.3801C18.7139 21.2649 18.7498 21.1337 18.75 21V4.5C18.75 4.10218 18.592 3.72064 18.3107 3.43934C18.0294 3.15804 17.6478 3 17.25 3ZM17.25 4.5V15.1472L12.3966 12.1144C12.2774 12.0399 12.1396 12.0004 11.9991 12.0004C11.8585 12.0004 11.7208 12.0399 11.6016 12.1144L6.75 15.1462V4.5H17.25ZM12.3966 16.6144C12.2774 16.5399 12.1396 16.5004 11.9991 16.5004C11.8585 16.5004 11.7208 16.5399 11.6016 16.6144L6.75 19.6472V16.9153L12 13.6341L17.25 16.9153V19.6472L12.3966 16.6144Z" fill="#1F2022"/>
                </svg>

              </button>
              <span class="tooltiptext text-xs bg-white rounded-xl mb-1 shadow-sm">Show History</span>
             </div>
            </div>
          </div>
        </div>
      </div>
    </teleport>
  </template>
  
  <script setup>
  import { defineProps, defineEmits } from 'vue';
  
  defineProps({
    isOpen: Boolean,
    imageSrc: String
  });
  
  const emit = defineEmits(['close']);
  
  const closeModal = () => {
    emit('close');
  };

  const isMuted = ref(false);

const toggleMic = () => {
  isMuted.value = !isMuted.value;
};
  </script>
  <style>
.tooltip {
  position: relative;
  display: inline-block;
}

.tooltip .tooltiptext {
  visibility: hidden;
  width: 120px;
  text-align: center;
  border-radius: 6px;
  padding: 8px 0;
  
  /* Position the tooltip */
  position: absolute;
  z-index: 1;
  bottom: 100%;
  left: 50%;
  margin-left: -60px;
}

.tooltip:hover .tooltiptext {
  visibility: visible;
}
</style>