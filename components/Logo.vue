<template>             
           
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
    </style>