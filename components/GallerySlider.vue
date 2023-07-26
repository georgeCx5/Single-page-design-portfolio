<script setup>
import { vAutoAnimate } from '@formkit/auto-animate'
</script>
<script>
import ArrowDirection from './ArrowDirection.vue'

export default {
   data() {
      return {
         data: [
            'bg-[url(@/assets/images/image-slide-1.jpg)]',
            'bg-[url(@/assets/images/image-slide-2.jpg)]',
            'bg-[url(@/assets/images/image-slide-3.jpg)]',
            'bg-[url(@/assets/images/image-slide-4.jpg)]',
            'bg-[url(@/assets/images/image-slide-5.jpg)]',
         ],
         countArr: [
            0,
            1,
            2,
            3,
            4
         ]
      }
   },
   components: {
      ArrowDirection,
   },
   methods: {
      increaseValue() {
         for (let i = 0; i < this.countArr.length; i++) {
            this.countArr[i] += 1
            if (this.countArr[i] >= this.countArr.length) {
               this.countArr[i] = 0
            }
         }
      },
      decreaseValue() {
         for (let i = 0; i < this.countArr.length; i++) {
            this.countArr[i] -= 1
            if (this.countArr[i] < 0) {
               this.countArr[i] = this.countArr.length - 1
            }
         }
      },
      setVisibility(value) {
         if (value >= this.countArr.length - 1 || value <= 0) {
            return 'invisible'
         }
      }
   }
}
</script>
<template>
   <div class=" flex flex-col items-center gap-8 TB:gap-14 overflow-hidden">
      <h2 class=" text-[24px] TB:text-[32px] leading-[30px] TB:leading-[40px] font-bold">
         My Work</h2>
      <div v-auto-animate class=" relative flex gap-4 TB:gap-[30px] w-[375%] TB:w-[367%] DT:w-[195%] h-[180px] TB:h-[360px]">
         <div v-for="(count, index) in countArr" :key="count"
            :class="` w-full h-full ${data[count]} bg-cover bg-center rounded-lg ${setVisibility(index)}`"></div>
      </div>
      <div @keydown.left="decreaseValue" @keydown.right="increaseValue" class=" flex gap-4 w-36 h-16">
         <ArrowDirection @click="decreaseValue" direction="left" />
         <ArrowDirection @click="increaseValue" direction="right" />
      </div>
   </div>
</template>