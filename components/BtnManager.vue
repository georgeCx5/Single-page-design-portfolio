<script>
export default {
   data() {
      return {

      }
   },
   computed: {
      getColor() {
         return this.isMain ? 'bg-neo-orange hover:bg-neo-yellow' : 'bg-neo-black hover:bg-neo-blue'
      }
   },
   props: {
      isMain: {
         Boolean,
         required: true,
      }
   }
}
</script>
<template>
   <button
      :class="` w-[176px] TB:w-[228px] h-11 TB:h-14 ${getColor} text-neo-transparent text-[.875rem] TB:text-[1rem] leading-7 font-bold rounded-[28px] select-none`">
      Free Consultation
   </button>
</template>