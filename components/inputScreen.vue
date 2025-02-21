<template>

<div class="flex flex-row items-center space-x-3 pb-10">
                <div class="bg-white rounded-full p-3">
                    <img src="../assets/icons/wechat.png" />
           
                </div>
                <div class="text-container">         
                        
                        <p class="text-effect">How Can I Help You Today?</p>
                           
                    </div>
    </div>
    <div class="">
      <div class="relative justify-center transition-all duration-300">
      <!-- Icon Bar - now positioned absolutely -->
        <div v-if="isExpanded" class="flex min-h-[50px] space-x-4 mx-36">
          <!-- Upload Icon -->
           <div class="w-[40px] h-[40px] p-2 justify-center items-center bg-white rounded-xl tooltip">
          <button class="transition-all duration-300 ease-in-out hover:bg-[#D9F27E] group rounded-full ">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M22.5 12.7501V18.7501C22.5 19.1479 22.342 19.5295 22.0607 19.8108C21.7794 20.0921 21.3978 20.2501 21 20.2501H3C2.60218 20.2501 2.22064 20.0921 1.93934 19.8108C1.65804 19.5295 1.5 19.1479 1.5 18.7501V12.7501C1.5 12.3523 1.65804 11.9707 1.93934 11.6894C2.22064 11.4081 2.60218 11.2501 3 11.2501H7.5C7.69891 11.2501 7.88968 11.3291 8.03033 11.4698C8.17098 11.6104 8.25 11.8012 8.25 12.0001C8.25 12.199 8.17098 12.3898 8.03033 12.5304C7.88968 12.6711 7.69891 12.7501 7.5 12.7501H3V18.7501H21V12.7501H16.5C16.3011 12.7501 16.1103 12.6711 15.9697 12.5304C15.829 12.3898 15.75 12.199 15.75 12.0001C15.75 11.8012 15.829 11.6104 15.9697 11.4698C16.1103 11.3291 16.3011 11.2501 16.5 11.2501H21C21.3978 11.2501 21.7794 11.4081 22.0607 11.6894C22.342 11.9707 22.5 12.3523 22.5 12.7501ZM8.03063 7.28073L11.25 4.06041V12.0001C11.25 12.199 11.329 12.3898 11.4697 12.5304C11.6103 12.6711 11.8011 12.7501 12 12.7501C12.1989 12.7501 12.3897 12.6711 12.5303 12.5304C12.671 12.3898 12.75 12.199 12.75 12.0001V4.06041L15.9694 7.28073C16.1101 7.42146 16.301 7.50052 16.5 7.50052C16.699 7.50052 16.8899 7.42146 17.0306 7.28073C17.1714 7.14 17.2504 6.94912 17.2504 6.7501C17.2504 6.55108 17.1714 6.36021 17.0306 6.21948L12.5306 1.71948C12.461 1.64974 12.3783 1.59443 12.2872 1.55668C12.1962 1.51894 12.0986 1.49951 12 1.49951C11.9014 1.49951 11.8038 1.51894 11.7128 1.55668C11.6217 1.59443 11.539 1.64974 11.4694 1.71948L6.96937 6.21948C6.82864 6.36021 6.74958 6.55108 6.74958 6.7501C6.74958 6.94912 6.82864 7.14 6.96938 7.28073C7.11011 7.42146 7.30098 7.50052 7.5 7.50052C7.69902 7.50052 7.88989 7.42146 8.03063 7.28073ZM18.75 15.7501C18.75 15.5276 18.684 15.3101 18.5604 15.1251C18.4368 14.9401 18.2611 14.7959 18.0555 14.7107C17.85 14.6256 17.6238 14.6033 17.4055 14.6467C17.1873 14.6901 16.9868 14.7973 16.8295 14.9546C16.6722 15.1119 16.565 15.3124 16.5216 15.5306C16.4782 15.7489 16.5005 15.9751 16.5856 16.1806C16.6708 16.3862 16.815 16.5619 17 16.6855C17.185 16.8091 17.4025 16.8751 17.625 16.8751C17.9234 16.8751 18.2095 16.7566 18.4205 16.5456C18.6315 16.3346 18.75 16.0485 18.75 15.7501Z" fill="#1F2022"/>
            </svg>
          </button>
          <span class="tooltiptext text-xs bg-white rounded-xl mb-1">Upload Document</span>
        </div>

          <!-- Download Icon -->
          <div class="w-[40px] h-[40px] p-2 justify-center items-center bg-white rounded-xl tooltip">
            <button class="transition-all duration-300 ease-in-out hover:bg-[#D9F27E] group rounded-full ">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M22.5 12.75V18.75C22.5 19.1478 22.342 19.5294 22.0607 19.8107C21.7794 20.092 21.3978 20.25 21 20.25H3C2.60218 20.25 2.22064 20.092 1.93934 19.8107C1.65804 19.5294 1.5 19.1478 1.5 18.75V12.75C1.5 12.3522 1.65804 11.9706 1.93934 11.6893C2.22064 11.408 2.60218 11.25 3 11.25H6.75C6.94891 11.25 7.13968 11.329 7.28033 11.4697C7.42098 11.6103 7.5 11.8011 7.5 12C7.5 12.1989 7.42098 12.3897 7.28033 12.5303C7.13968 12.671 6.94891 12.75 6.75 12.75H3V18.75H21V12.75H17.25C17.0511 12.75 16.8603 12.671 16.7197 12.5303C16.579 12.3897 16.5 12.1989 16.5 12C16.5 11.8011 16.579 11.6103 16.7197 11.4697C16.8603 11.329 17.0511 11.25 17.25 11.25H21C21.3978 11.25 21.7794 11.408 22.0607 11.6893C22.342 11.9706 22.5 12.3522 22.5 12.75ZM11.4694 12.5306C11.539 12.6004 11.6217 12.6557 11.7128 12.6934C11.8038 12.7312 11.9014 12.7506 12 12.7506C12.0986 12.7506 12.1962 12.7312 12.2872 12.6934C12.3783 12.6557 12.461 12.6004 12.5306 12.5306L17.0306 8.03063C17.1714 7.88989 17.2504 7.69902 17.2504 7.5C17.2504 7.30098 17.1714 7.11011 17.0306 6.96937C16.8899 6.82864 16.699 6.74958 16.5 6.74958C16.301 6.74958 16.1101 6.82864 15.9694 6.96937L12.75 10.1897V2.25C12.75 2.05109 12.671 1.86032 12.5303 1.71967C12.3897 1.57902 12.1989 1.5 12 1.5C11.8011 1.5 11.6103 1.57902 11.4697 1.71967C11.329 1.86032 11.25 2.05109 11.25 2.25V10.1897L8.03063 6.96937C7.88989 6.82864 7.69902 6.74958 7.5 6.74958C7.30098 6.74958 7.11011 6.82864 6.96938 6.96938C6.82864 7.11011 6.74958 7.30098 6.74958 7.5C6.74958 7.69902 6.82864 7.88989 6.96937 8.03063L11.4694 12.5306ZM18.75 15.75C18.75 15.5275 18.684 15.31 18.5604 15.125C18.4368 14.94 18.2611 14.7958 18.0555 14.7106C17.85 14.6255 17.6238 14.6032 17.4055 14.6466C17.1873 14.69 16.9868 14.7972 16.8295 14.9545C16.6722 15.1118 16.565 15.3123 16.5216 15.5305C16.4782 15.7488 16.5005 15.975 16.5856 16.1805C16.6708 16.3861 16.815 16.5618 17 16.6854C17.185 16.809 17.4025 16.875 17.625 16.875C17.9234 16.875 18.2095 16.7565 18.4205 16.5455C18.6315 16.3345 18.75 16.0484 18.75 15.75Z" fill="#1F2022"/>
            </svg>
          </button>
          <span class="tooltiptext text-xs bg-white rounded-xl mb-1">Download Chat</span>

          </div>
          <!-- Refresh Icon -->
           <div class="w-[40px] h-[40px] p-2 justify-center items-center bg-white rounded-xl tooltip">
          <button class="transition-all duration-300 ease-in-out hover:bg-[#D9F27E] group rounded-full ">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M22.4995 5.25013V9.75013C22.4995 9.94905 22.4205 10.1398 22.2799 10.2805C22.1392 10.4211 21.9484 10.5001 21.7495 10.5001H17.2495C17.0506 10.5001 16.8598 10.4211 16.7192 10.2805C16.5785 10.1398 16.4995 9.94905 16.4995 9.75013C16.4995 9.55122 16.5785 9.36046 16.7192 9.2198C16.8598 9.07915 17.0506 9.00013 17.2495 9.00013H19.8183L17.3255 6.71638L17.302 6.69388C16.2596 5.65184 14.9332 4.94006 13.4886 4.64746C12.044 4.35485 10.5452 4.4944 9.17942 5.04866C7.81365 5.60293 6.64148 6.54734 5.80934 7.76391C4.97719 8.98048 4.52196 10.4153 4.50052 11.8891C4.47907 13.3629 4.89237 14.8103 5.68877 16.0506C6.48517 17.2908 7.62937 18.269 8.97843 18.8627C10.3275 19.4565 11.8216 19.6396 13.2741 19.3891C14.7266 19.1387 16.0731 18.4658 17.1455 17.4545C17.29 17.3178 17.483 17.244 17.682 17.2496C17.8809 17.2551 18.0695 17.3395 18.2062 17.484C18.343 17.6286 18.4167 17.8216 18.4112 18.0205C18.4056 18.2195 18.3213 18.4081 18.1767 18.5448C16.5093 20.1261 14.2975 21.0053 11.9995 21.0001H11.8758C10.4018 20.9799 8.9553 20.598 7.66349 19.8879C6.37167 19.1777 5.27406 18.1612 4.46714 16.9275C3.66021 15.6938 3.16866 14.2808 3.03571 12.8127C2.90275 11.3446 3.13245 9.86628 3.70462 8.50772C4.27679 7.14916 5.17391 5.95194 6.31714 5.02128C7.46036 4.09063 8.81468 3.45504 10.2611 3.17038C11.7075 2.88571 13.2016 2.96069 14.6122 3.38871C16.0229 3.81674 17.3068 4.58471 18.3511 5.62513L20.9995 8.04388V5.25013C20.9995 5.05122 21.0785 4.86046 21.2192 4.7198C21.3598 4.57915 21.5506 4.50013 21.7495 4.50013C21.9484 4.50013 22.1392 4.57915 22.2799 4.7198C22.4205 4.86046 22.4995 5.05122 22.4995 5.25013Z" fill="#1F2022"/>
            </svg>
          </button>
          <span class="tooltiptext text-xs bg-white rounded-xl mb-1">Refresh Chat</span>
          </div>

          <!-- Globe/Language Icon -->
           <div class="w-[40px] h-[40px] p-2 justify-center items-center bg-white rounded-xl tooltip">
          <button class="transition-all duration-300 ease-in-out hover:bg-[#D9F27E] group rounded-full ">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M12 22C17.5228 22 22 17.5228 22 12C22 6.47715 17.5228 2 12 2C6.47715 2 2 6.47715 2 12C2 17.5228 6.47715 22 12 22Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              <path d="M2 12H22M12 2C14.5013 4.73835 15.9228 8.29203 16 12C15.9228 15.708 14.5013 19.2616 12 22C9.49872 19.2616 8.07725 15.708 8 12C8.07725 8.29203 9.49872 4.73835 12 2Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
          <span class="tooltiptext text-xs bg-white rounded-xl mb-1">Search</span>
          </div>

          <!-- Grid/Menu Icon -->
           <div class="w-[40px] h-[40px] p-2 justify-center items-center bg-white rounded-xl tooltip">
          <button class="transition-all duration-300 ease-in-out hover:bg-[#D9F27E] group rounded-full ">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M9.75 3.75H5.25C4.85218 3.75 4.47064 3.90804 4.18934 4.18934C3.90804 4.47064 3.75 4.85218 3.75 5.25V9.75C3.75 10.1478 3.90804 10.5294 4.18934 10.8107C4.47064 11.092 4.85218 11.25 5.25 11.25H9.75C10.1478 11.25 10.5294 11.092 10.8107 10.8107C11.092 10.5294 11.25 10.1478 11.25 9.75V5.25C11.25 4.85218 11.092 4.47064 10.8107 4.18934C10.5294 3.90804 10.1478 3.75 9.75 3.75ZM9.75 9.75H5.25V5.25H9.75V9.75ZM18.75 3.75H14.25C13.8522 3.75 13.4706 3.90804 13.1893 4.18934C12.908 4.47064 12.75 4.85218 12.75 5.25V9.75C12.75 10.1478 12.908 10.5294 13.1893 10.8107C13.4706 11.092 13.8522 11.25 14.25 11.25H18.75C19.1478 11.25 19.5294 11.092 19.8107 10.8107C20.092 10.5294 20.25 10.1478 20.25 9.75V5.25C20.25 4.85218 20.092 4.47064 19.8107 4.18934C19.5294 3.90804 19.1478 3.75 18.75 3.75ZM18.75 9.75H14.25V5.25H18.75V9.75ZM9.75 12.75H5.25C4.85218 12.75 4.47064 12.908 4.18934 13.1893C3.90804 13.4706 3.75 13.8522 3.75 14.25V18.75C3.75 19.1478 3.90804 19.5294 4.18934 19.8107C4.47064 20.092 4.85218 20.25 5.25 20.25H9.75C10.1478 20.25 10.5294 20.092 10.8107 19.8107C11.092 19.5294 11.25 19.1478 11.25 18.75V14.25C11.25 13.8522 11.092 13.4706 10.8107 13.1893C10.5294 12.908 10.1478 12.75 9.75 12.75ZM9.75 18.75H5.25V14.25H9.75V18.75ZM18.75 12.75H14.25C13.8522 12.75 13.4706 12.908 13.1893 13.1893C12.908 13.4706 12.75 13.8522 12.75 14.25V18.75C12.75 19.1478 12.908 19.5294 13.1893 19.8107C13.4706 20.092 13.8522 20.25 14.25 20.25H18.75C19.1478 20.25 19.5294 20.092 19.8107 19.8107C20.092 19.5294 20.25 19.1478 20.25 18.75V14.25C20.25 13.8522 20.092 13.4706 19.8107 13.1893C19.5294 12.908 19.1478 12.75 18.75 12.75ZM18.75 18.75H14.25V14.25H18.75V18.75Z" fill="#1F2022"/>
            </svg>
          </button>
          <span class="tooltiptext text-xs bg-white rounded-xl mb-1">Multi-Mode</span>
          </div>
        

          <!-- Command/Shortcut Icon -->
           <div class="w-[40px] h-[40px] p-2 justify-center items-center bg-white rounded-xl tooltip">
          <button class="transition-all duration-300 ease-in-out hover:bg-[#D9F27E] group rounded-full ">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M18 3a3 3 0 0 0-3 3v12a3 3 0 0 0 3 3 3 3 0 0 0 3-3 3 3 0 0 0-3-3H6a3 3 0 0 0-3 3 3 3 0 0 0 3 3 3 3 0 0 0 3-3V6a3 3 0 0 0-3-3 3 3 0 0 0-3 3 3 3 0 0 0 3 3h12a3 3 0 0 0 3-3 3 3 0 0 0-3-3z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
          <span class="tooltiptext text-xs bg-white rounded-xl mb-1">Custom Command</span>
          </div>


          <!-- Chat/User Icon -->
           <div class="w-[40px] h-[40px] p-2 justify-center items-center bg-white rounded-xl tooltip">
          <button class="transition-all duration-300 ease-in-out hover:bg-[#D9F27E] group rounded-full ">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M13.5 15.5323C14.6757 14.8001 15.5809 13.7048 16.0787 12.4122C16.5765 11.1197 16.6398 9.70013 16.259 8.36839C15.8782 7.03666 15.074 5.86518 13.9681 5.0312C12.8622 4.19721 11.5148 3.74609 10.1296 3.74609C8.74453 3.74609 7.3971 4.19721 6.29121 5.0312C5.18531 5.86518 4.38112 7.03666 4.00031 8.36839C3.6195 9.70013 3.68278 11.1197 4.18058 12.4122C4.67838 13.7048 5.58361 14.8001 6.75933 15.5323C4.82339 16.1661 3.08151 17.3502 1.68089 19.017C1.55284 19.1693 1.49053 19.3662 1.50767 19.5645C1.52482 19.7627 1.62 19.946 1.7723 20.0741C1.92459 20.2021 2.12151 20.2644 2.31974 20.2473C2.51797 20.2301 2.70128 20.1349 2.82933 19.9827C4.71089 17.7364 7.30401 16.4998 10.125 16.4998C12.9459 16.4998 15.539 17.7364 17.4262 19.9827C17.5543 20.1349 17.7376 20.2301 17.9358 20.2473C18.134 20.2644 18.3309 20.2021 18.4832 20.0741C18.6355 19.946 18.7307 19.7627 18.7479 19.5645C18.765 19.3662 18.7027 19.1693 18.5746 19.017C17.1731 17.3502 15.4312 16.1661 13.5 15.5323ZM5.24995 10.1248C5.24995 9.16066 5.53587 8.21813 6.07154 7.41644C6.60721 6.61475 7.36858 5.98991 8.25937 5.62093C9.15016 5.25195 10.1304 5.15541 11.076 5.34351C12.0217 5.53162 12.8903 5.99592 13.5721 6.6777C14.2539 7.35948 14.7182 8.22812 14.9063 9.17378C15.0944 10.1194 14.9978 11.0996 14.6289 11.9904C14.2599 12.8812 13.635 13.6426 12.8334 14.1783C12.0317 14.7139 11.0891 14.9998 10.125 14.9998C8.83248 14.9984 7.59337 14.4843 6.67945 13.5703C5.76553 12.6564 5.25144 11.4173 5.24995 10.1248ZM19.44 6.14984C19.9744 7.40691 20.2499 8.75886 20.2499 10.1248C20.2499 11.4908 19.9744 12.8428 19.44 14.0998C19.3823 14.2351 19.2861 14.3503 19.1634 14.4313C19.0407 14.5123 18.897 14.5555 18.75 14.5555C18.6258 14.5556 18.5036 14.5248 18.3942 14.4661C18.2849 14.4073 18.1918 14.3223 18.1234 14.2186C18.055 14.115 18.0134 13.9961 18.0024 13.8724C17.9913 13.7487 18.0111 13.6243 18.06 13.5102C18.5153 12.4396 18.75 11.2882 18.75 10.1248C18.75 8.96148 18.5153 7.81008 18.06 6.73953C17.9818 6.55653 17.9795 6.34996 18.0536 6.16527C18.1277 5.98058 18.2721 5.83288 18.4551 5.75469C18.6381 5.67649 18.8447 5.67419 19.0294 5.7483C19.2141 5.8224 19.3618 5.96684 19.44 6.14984ZM23.25 10.1248C23.2535 11.9024 22.8933 13.6619 22.1915 15.2952C22.1094 15.4722 21.9616 15.6102 21.7794 15.68C21.5972 15.7498 21.395 15.7459 21.2157 15.669C21.0363 15.5921 20.894 15.4484 20.8189 15.2684C20.7438 15.0883 20.7418 14.886 20.8134 14.7045C21.4314 13.2568 21.75 11.699 21.75 10.1248C21.75 8.55073 21.4314 6.99289 20.8134 5.54516C20.7712 5.45413 20.7477 5.35555 20.7442 5.25527C20.7408 5.15498 20.7575 5.05503 20.7934 4.96133C20.8293 4.86763 20.8837 4.78208 20.9532 4.70976C21.0228 4.63743 21.1061 4.5798 21.1984 4.54028C21.2906 4.50075 21.3898 4.48013 21.4901 4.47964C21.5905 4.47916 21.6899 4.49881 21.7825 4.53744C21.8751 4.57606 21.959 4.63288 22.0293 4.70453C22.0995 4.77617 22.1547 4.86118 22.1915 4.95453C22.8933 6.58774 23.2535 8.34725 23.25 10.1248Z" fill="#1F2022"/>
            </svg>
          </button>
          <span class="tooltiptext text-xs bg-white rounded-xl mb-1">Voice</span>
          </div>

          <!-- Edit Icon (Highlighted) -->
           <div class="w-[40px] h-[40px] p-1 justify-center items-center bg-white rounded-xl tooltip">
          <button class="transition-all duration-300 ease-in-out hover:bg-[#D9F27E] group rounded-full ">
            <svg width="32" height="32" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M28.4138 9.17122L22.8288 3.58497C22.643 3.39921 22.4225 3.25185 22.1799 3.15131C21.9372 3.05077 21.6771 2.99902 21.4144 2.99902C21.1517 2.99902 20.8916 3.05077 20.6489 3.15131C20.4062 3.25185 20.1857 3.39921 20 3.58497L4.58626 19C4.39973 19.185 4.25185 19.4053 4.15121 19.648C4.05057 19.8907 3.99917 20.151 4.00001 20.4137V26C4.00001 26.5304 4.21072 27.0391 4.5858 27.4142C4.96087 27.7893 5.46958 28 6.00001 28H11.5863C11.849 28.0008 12.1093 27.9494 12.352 27.8488C12.5947 27.7481 12.815 27.6002 13 27.4137L28.4138 12C28.5995 11.8142 28.7469 11.5937 28.8474 11.3511C28.948 11.1084 28.9997 10.8483 28.9997 10.5856C28.9997 10.3229 28.948 10.0628 28.8474 9.82012C28.7469 9.57744 28.5995 9.35694 28.4138 9.17122ZM6.41376 20L17 9.41372L19.0863 11.5L8.50001 22.085L6.41376 20ZM6.00001 22.4137L9.58626 26H6.00001V22.4137ZM12 25.5862L9.91376 23.5L20.5 12.9137L22.5863 15L12 25.5862ZM24 13.5862L18.4138 7.99997L21.4138 4.99997L27 10.585L24 13.5862Z" fill="#1F2022"/>
            </svg>
          </button>
          <span class="tooltiptext text-xs bg-white rounded-xl mb-1">Open in Canva</span>
          </div>
        </div>          
    </div>
    <div class="flex items-start lg:w-2/3" >
    <div 
    @click="toggleExpand"
    class="bg-white w-[40px] h-[40px] p-2 justify-center items-center rounded-full mx-3 mt-5 cursor-pointer"
    :class="{ 'rotate-180': isExpanded }"
    >
      <button class="transition-all duration-300 ease-in-out hover:bg-[#D9F27E] group rounded-full">
      <svg width="24" height="25" viewBox="0 0 24 25" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M20.0306 16.0306C19.961 16.1003 19.8782 16.1557 19.7872 16.1934C19.6961 16.2311 19.5986 16.2506 19.5 16.2506C19.4014 16.2506 19.3038 16.2311 19.2128 16.1934C19.1217 16.1557 19.039 16.1003 18.9694 16.0306L12 9.06029L5.03061 16.0306C4.88988 16.1713 4.69901 16.2504 4.49999 16.2504C4.30097 16.2504 4.1101 16.1713 3.96936 16.0306C3.82863 15.8899 3.74957 15.699 3.74957 15.5C3.74957 15.301 3.82863 15.1101 3.96936 14.9694L11.4694 7.46935C11.539 7.39962 11.6217 7.3443 11.7128 7.30656C11.8038 7.26882 11.9014 7.24939 12 7.24939C12.0986 7.24939 12.1961 7.26882 12.2872 7.30656C12.3782 7.3443 12.461 7.39962 12.5306 7.46935L20.0306 14.9694C20.1003 15.039 20.1557 15.1217 20.1934 15.2128C20.2312 15.3038 20.2506 15.4014 20.2506 15.5C20.2506 15.5985 20.2312 15.6961 20.1934 15.7872C20.1557 15.8782 20.1003 15.9609 20.0306 16.0306Z" fill="#1F2022"/>
      </svg>
    </button>
    </div>

    <div class="flex-1">
      <form class="flex items-center w-full" @submit.prevent>   
        <div class="relative w-full" @dblclick="emitToggle">
          <div v-if="!isVoiceOpen" class="absolute  left-3 top-1/2 -translate-y-1/2 z-10">
            <button 
            @click="openVoiceDialog"  
              class="p-2 transition-all duration-300 ease-in-out hover:bg-[#D9F27E] group rounded-full"
            >
              <svg class="w-8 h-8" width="24" height="25" viewBox="0 0 24 25" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 17C13.1931 16.9988 14.337 16.5243 15.1806 15.6806C16.0243 14.837 16.4988 13.6931 16.5 12.5V6.5C16.5 5.30653 16.0259 4.16193 15.182 3.31802C14.3381 2.47411 13.1935 2 12 2C10.8065 2 9.66193 2.47411 8.81802 3.31802C7.97411 4.16193 7.5 5.30653 7.5 6.5V12.5C7.50124 13.6931 7.97575 14.837 8.81939 15.6806C9.66303 16.5243 10.8069 16.9988 12 17ZM9 6.5C9 5.70435 9.31607 4.94129 9.87868 4.37868C10.4413 3.81607 11.2044 3.5 12 3.5C12.7956 3.5 13.5587 3.81607 14.1213 4.37868C14.6839 4.94129 15 5.70435 15 6.5V12.5C15 13.2956 14.6839 14.0587 14.1213 14.6213C13.5587 15.1839 12.7956 15.5 12 15.5C11.2044 15.5 10.4413 15.1839 9.87868 14.6213C9.31607 14.0587 9 13.2956 9 12.5V6.5ZM12.75 19.9625V23C12.75 23.1989 12.671 23.3897 12.5303 23.5303C12.3897 23.671 12.1989 23.75 12 23.75C11.8011 23.75 11.6103 23.671 11.4697 23.5303C11.329 23.3897 11.25 23.1989 11.25 23V19.9625C9.40091 19.7743 7.68728 18.9072 6.44048 17.5288C5.19368 16.1504 4.50228 14.3586 4.5 12.5C4.5 12.3011 4.57902 12.1103 4.71967 11.9697C4.86032 11.829 5.05109 11.75 5.25 11.75C5.44891 11.75 5.63968 11.829 5.78033 11.9697C5.92098 12.1103 6 12.3011 6 12.5C6 14.0913 6.63214 15.6174 7.75736 16.7426C8.88258 17.8679 10.4087 18.5 12 18.5C13.5913 18.5 15.1174 17.8679 16.2426 16.7426C17.3679 15.6174 18 14.0913 18 12.5C18 12.3011 18.079 12.1103 18.2197 11.9697C18.3603 11.829 18.5511 11.75 18.75 11.75C18.9489 11.75 19.1397 11.829 19.2803 11.9697C19.421 12.1103 19.5 12.3011 19.5 12.5C19.4977 14.3586 18.8063 16.1504 17.5595 17.5288C16.3127 18.9072 14.5991 19.7743 12.75 19.9625Z" fill="#5B626B"/>
              </svg>
            
              <svg class="absolute top-0 left-0 w-4 h-4 text-gray-500" width="12" height="13" viewBox="0 0 12 13" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M9.75 4.15H8.35V3.125C8.35 2.50174 8.10241 1.90401 7.6617 1.4633C7.22099 1.02259 6.62326 0.775 6 0.775C5.37674 0.775 4.77901 1.02259 4.3383 1.4633C3.89759 1.90401 3.65 2.50174 3.65 3.125V4.15H2.25C2.02457 4.15 1.80837 4.23955 1.64896 4.39896C1.48955 4.55837 1.4 4.77457 1.4 5V10.25C1.4 10.4754 1.48955 10.6916 1.64896 10.851C1.80837 11.0104 2.02457 11.1 2.25 11.1H9.75C9.97543 11.1 10.1916 11.0104 10.351 10.851C10.5104 10.6916 10.6 10.4754 10.6 10.25V5C10.6 4.77457 10.5104 4.55837 10.351 4.39896C10.1916 4.23955 9.97543 4.15 9.75 4.15ZM4.6 3.125C4.6 2.7537 4.7475 2.3976 5.01005 2.13505C5.2726 1.8725 5.6287 1.725 6 1.725C6.3713 1.725 6.7274 1.8725 6.98995 2.13505C7.2525 2.3976 7.4 2.7537 7.4 3.125V4.15H4.6V3.125ZM2.35 10.15V5.1H9.65V10.15H2.35Z" fill="#5B626B" stroke="#5B626B" stroke-width="0.2"/>
</svg>
            </button>
          </div>
          <div class="relative">
    <button @click.prevent="emitToggle" class="absolute right-4 my-7 text-gray-500">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M20.7806 12.5307L14.0306 19.2807C13.8899 19.4214 13.699 19.5005 13.5 19.5005C13.301 19.5005 13.1101 19.4214 12.9694 19.2807C12.8286 19.1399 12.7496 18.9491 12.7496 18.7501C12.7496 18.551 12.8286 18.3602 12.9694 18.2194L18.4397 12.7501H3.75C3.55109 12.7501 3.36032 12.671 3.21967 12.5304C3.07902 12.3897 3 12.199 3 12.0001C3 11.8011 3.07902 11.6104 3.21967 11.4697C3.36032 11.3291 3.55109 11.2501 3.75 11.2501H18.4397L12.9694 5.78068C12.8286 5.63995 12.7496 5.44907 12.7496 5.25005C12.7496 5.05103 12.8286 4.86016 12.9694 4.71943C13.1101 4.5787 13.301 4.49963 13.5 4.49963C13.699 4.49963 13.8899 4.5787 14.0306 4.71943L20.7806 11.4694C20.8504 11.5391 20.9057 11.6218 20.9434 11.7128C20.9812 11.8039 21.0006 11.9015 21.0006 12.0001C21.0006 12.0986 20.9812 12.1962 20.9434 12.2873C20.9057 12.3783 20.8504 12.461 20.7806 12.5307Z" fill="#1F2022"/>
</svg>

    </button>
  </div>

          <input 
            type="text" 
            v-model="question" 
            @keyup.enter="emitToggle"
            id="simple-search" 
            class="h-20 bg-white w-[609px] pl-20 pr-4 rounded-3xl border-0" 
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
  </div>
            
            <div class="text-xs sm:text-sm py-2 tooltip">
              <button class="">
                <p class="text-gray-400">AskAIs can make mistakes. Check important info.</p>
              </button>
              <span class="tooltiptext text-xs !w-[300px] bg-white rounded-xl mb-1 shadow-md !p-5">
              <p class="text-xs">Company Information Line 1</p>
              <p>Company Information Line 2</p>
              <a href="#" class="underline mx-2">
                Terms of Services
              </a>
              <a href="#" class="underline mx-2">
             Privacy Terms
              </a>
            </span>
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
const isExpanded = ref(false)

const toggleExpand = () => {
  isExpanded.value = !isExpanded.value
}
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
