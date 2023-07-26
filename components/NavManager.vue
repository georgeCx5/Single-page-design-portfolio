<script>
import BtnManager from '@/components/BtnManager.vue'

import logo from '@/assets/images/logo.svg?url'
export default {
   data() {
      return {
         logo,
      }
   },
   components: {
      BtnManager,
   }
}
</script>
<template>
   <img class=" h-12 select-none" :src="logo" alt="logo" draggable="false">
   <BtnManager :isMain="false" />
</template>