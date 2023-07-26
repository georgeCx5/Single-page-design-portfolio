<script>
export default {
   data() {
      return {
         data: [
            'bg-[url(@/assets/images/image-slide-1.jpg)]',
            'bg-[url(@/assets/images/image-slide-2.jpg)]',
            'bg-[url(@/assets/images/image-slide-3.jpg)]',
            'bg-[url(@/assets/images/image-slide-4.jpg)]',
            'bg-[url(@/assets/images/image-slide-5.jpg)]',
         ]
      }
   },
   props: {
      dataIndex: {
         Number,
         required: true,
      }
   }
}
</script>
<template>
   <div :class="` w-full h-full ${data[dataIndex]} bg-cover rounded-lg`"></div>
</template>