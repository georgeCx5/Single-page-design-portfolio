<script>
import arrowLeft from '@/assets/images/icon-arrow-left.svg?url'
import arrowRight from '@/assets/images/icon-arrow-right.svg?url'

export default {
   data() {
      return {
      }
   },
   computed: {
      getDirection() {
         if (this.direction == 'left') return arrowLeft
         if (this.direction == 'right') return arrowRight
      }
   },
   props: {
      direction: {
         String,
         required: true,
      }
   }
}
</script>
<template>
   <button class=" flex justify-center items-center w-full h-full bg-neo-black hover:bg-neo-blue focus:outline-none rounded-full select-none">
      <img :src="getDirection" alt="arrow">
   </button>
</template>