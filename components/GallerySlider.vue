<script>
import ImageActive from './ImageActive.vue'
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
            2
         ]
      }
   },
   components: {
      ImageActive,
      ArrowDirection,
   },
   methods: {
      increaseValue() {
         for (let i = 0; i < this.countArr.length; i++) {
            this.countArr[i] += 1
            if (this.countArr[i] >= this.data.length) {
               this.countArr[i] = 0
            }
         }
      },
      decreaseValue() {
         for (let i = 0; i < this.countArr.length; i++) {
            this.countArr[i] -= 1
            if (this.countArr[i] < 0) {
               this.countArr[i] = this.data.length - 1
            }
         }
      }
   }
}
</script>
<template>
   <div class=" flex flex-col items-center gap-8 overflow-hidden">
      <h2 class=" text-[24px] leading-[30px] font-bold">
         My Work</h2>
      <div class=" flex gap-4 w-[840px] h-[180px]">
         <ImageActive :data-index="countArr[0]" />
         <ImageActive :data-index="countArr[1]" />
         <ImageActive :data-index="countArr[2]" />
      </div>
      <div class=" flex gap-4 w-36 h-16">
         <ArrowDirection @click="decreaseValue" direction="left" />
         <ArrowDirection @click="increaseValue" direction="right" />
      </div>
   </div>
</template>