<script>
import pGraphicDesign from '@/assets/images/pattern-graphic-design.svg?url'
import pUiUx from '@/assets/images/pattern-ui-ux.svg?url'
import pApps from '@/assets/images/pattern-apps.svg?url'
import pIllustrations from '@/assets/images/pattern-illustrations.svg?url'
import pPhotography from '@/assets/images/pattern-photography.svg?url'
import pMotionGraphics from '@/assets/images/pattern-motion-graphics.svg?url'

export default {
   data() {
      return {
         data: [
            {
               icon: pGraphicDesign,
               text: 'Graphic Design',
               bgColor: 'bg-neo-blue',
               gridTemplate: 'col-span-2 row-span-2 gap-24',
            },
            {
               icon: pUiUx,
               text: 'UI/UX',
               bgColor: 'bg-neo-yellow',
               gridTemplate: 'col-span-1 gap-10',
            },
            {
               icon: pApps,
               text: 'Apps',
               bgColor: 'bg-neo-pink',
               gridTemplate: 'col-span-1 gap-10',
            },
            {
               icon: pIllustrations,
               text: 'Illustrations',
               bgColor: 'bg-neo-orange',
               gridTemplate: 'col-span-2 DT:order-5 gap-4',
            },
            {
               icon: pPhotography,
               text: 'Photography',
               bgColor: 'bg-neo-green',
               gridTemplate: 'col-span-2 DT:order-4 gap-10',
            },
            {
               icon: pMotionGraphics,
               text: 'Motion Graphics',
               bgColor: 'bg-neo-purple',
               gridTemplate: 'col-span-2 DT:order-last gap-10',
            },
         ]
      }
   },
   props: {
      dataIndex: {
         Number,
         default: 0,
      }
   }
}
</script>
<template>
   <div
      :class="` ${data[dataIndex].gridTemplate} flex flex-col justify-between items-start h-full w-full p-6 ${data[dataIndex].bgColor} rounded-[8px]`">
      <img class=" self-end select-none" :src="data[dataIndex].icon" :alt="`Icon ${dataIndex}`" draggable="false">
      <h3 class=" flex text-neo-transparent text-[24px] leading-[30px] font-bold">
         {{ data[dataIndex].text }}</h3>
   </div>
</template>