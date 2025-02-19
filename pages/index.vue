<script setup lang="ts">
import { ref } from 'vue';
// import { Style } from "#components"

interface Message {
  text: string;
  sender: 'user' | 'bot';
}

const messages = ref<Message[]>([]);
const input = ref<string>('');
const isProcessing = ref<boolean>(false);

const sendMessage = async (): Promise<void> => {
  if (!input.value.trim()) return;

  messages.value.push({ text: input.value, sender: 'user' });
  input.value = '';
  isProcessing.value = true;

  setTimeout(() => {
    messages.value.push({ text: 'This is a bot response.', sender: 'bot' });
    isProcessing.value = false;
  }, 2000);
};
</script>




<template>
    
    <div class="p-4 sm:ml-64">
        <div class="h-screen  items-center flex flex-col justify-center">
            
            <!-- Logo  -->
             
            <!-- <div class="">
                <div class="bg-white rounded-full p-3">
                    <img src="../assets/icons/wechat.png" />
           
                </div>
    </div>
    <div class="text-container">         
                    <span class="flex flex-row pt-3">
                        
    <p class="text-effect">How Can I Help You Today?</p>

       
    </span>
</div> -->

          

            <!-- Input Command -->
            <!-- <div class="flex items-start lg:w-2/3 w-full pt-10">
    <div class="bg-white p-2 rounded-full mx-3">
      <svg width="24" height="25" viewBox="0 0 24 25" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M20.0306 16.0306C19.961 16.1003 19.8782 16.1557 19.7872 16.1934C19.6961 16.2311 19.5986 16.2506 19.5 16.2506C19.4014 16.2506 19.3038 16.2311 19.2128 16.1934C19.1217 16.1557 19.039 16.1003 18.9694 16.0306L12 9.06029L5.03061 16.0306C4.88988 16.1713 4.69901 16.2504 4.49999 16.2504C4.30097 16.2504 4.1101 16.1713 3.96936 16.0306C3.82863 15.8899 3.74957 15.699 3.74957 15.5C3.74957 15.301 3.82863 15.1101 3.96936 14.9694L11.4694 7.46935C11.539 7.39962 11.6217 7.3443 11.7128 7.30656C11.8038 7.26882 11.9014 7.24939 12 7.24939C12.0986 7.24939 12.1961 7.26882 12.2872 7.30656C12.3782 7.3443 12.461 7.39962 12.5306 7.46935L20.0306 14.9694C20.1003 15.039 20.1557 15.1217 20.1934 15.2128C20.2312 15.3038 20.2506 15.4014 20.2506 15.5C20.2506 15.5985 20.2312 15.6961 20.1934 15.7872C20.1557 15.8782 20.1003 15.9609 20.0306 16.0306Z" fill="#1F2022"/>
      </svg>
    </div>
    <div class="flex-1">
        <form class="flex items-center max-w" @submit.prevent="sendMessage">   
        <div class="relative w-full">
          <input 
            v-model="input" 
            id="simple-search" 
            type="text" 
            class="h-20 bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-xl focus:ring-blue-500 focus:border-blue-500 block w-full ps-10 p-2.5 pr-14" 
            placeholder="Input Command" 
            required 
          />
          <button type="submit" class="absolute inset-y-0 right-3 flex items-center">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" fill="#5B626B" class="w-6 h-6 cursor-pointer">
              <path d="M438.6 278.6c12.5-12.5 12.5-32.8 0-45.3l-160-160c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L338.8 224 32 224c-17.7 0-32 14.3-32 32s14.3 32 32 32l306.7 0L233.4 393.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0l160-160z"/>
            </svg>
          </button>
        </div>
      </form>
      
      <div v-if="isProcessing" class="mt-4 text-gray-500 bg-white p-6 rounded-xl shadow-md">Processing...</div>
      <div v-for="(message, index) in messages" :key="index" class="mt-4 p-6 rounded-xl shadow-md" :class="message.sender === 'user' ? 'text-blue-600 bg-blue-100 justify-end' : 'text-gray-900 bg-white justify-start'">
        {{ message.text }}
      </div>
    </div>
  </div> -->

 <div class="pt-100">
    <div class="bg-white text-black rounded-lg shadow-sm w-[668px] h-[51px] mb-4">
        <p class="px-3 py-3">I Can Help! Here is a button code.</p>
    </div>
    <div class="bg-white text-black rounded-lg hover:shadow-sm w-[668px] h-[577px] justify-center items-center px-4">
        <p class="px-3 py-3">/* Button Styling */</p>
        <div class="bg-gray-200 text-black  rounded-lg w-[636px] h-[355px] justify-center items-center pb-3">
            <pre class=" text-sm px-3 py-3">
.button {
  background-color: #007bff; /* Primary color */
  color: white;
  padding: 10px 20px;
  font-size: 16px;
  font-weight: bold;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
/* Hover Effect */
.button:hover {
  background-color: #0056b3; /* Darker shade on hover */
  box-shadow: 0 6px 8px rgba(0, 0, 0, 0.1);
}
        </pre>
        </div>
        <div class="">
        <pre class="pt-15">
You can copy the code above to build functional buttons with a nice 
hover effect
        </pre>
    </div>
    </div>
 </div>


            
            <!-- Info Text -->
            <!-- <div class="text-xs sm:text-sm py-2 ">
                <p class="text-gray-400">AskAIs can make mistakes. Check important info.</p>
            </div> -->
 <!-- dfd -->
            <!-- Suggestion Box -->
            <!-- <div class="w-5/6 p-2 mt-20 hidden sm:block bg-white border border-gray-200 rounded-lg shadow-sm dark:bg-gray-800 dark:border-gray-700">
                <div class="h-auto grid grid-cols-12">
                    <div class="col-span-4 p-3 h-72 overflow-y-auto [-ms-overflow-style:'none'] [scrollbar-width:'none'] [&::-webkit-scrollbar]:hidden"> -->
                        <!-- <h5 class="mb-2 text-md font-bold tracking-tight text-gray-900 dark:text-white">Suggest for you</h5>
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
                        </div> -->

                        <!-- Video Section -->
                        <!-- <h5 class="my-2 text-md font-bold tracking-tight text-gray-900 dark:text-white">Videos</h5>
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
                        </div> -->


                    <!-- </div>
                </div>
                
            </div> -->


        </div>
    </div>
  </template>


<!-- <script lang="ts" setup>
const question = ref('');
</script>


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
        animation: textAppear 5s steps(300) forwards;
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
</style> -->