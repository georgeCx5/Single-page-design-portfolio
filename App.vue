<script>
import NavManager from './components/NavManager.vue';
import MainGrid from './components/MainGrid.vue';
import BtnManager from './components/BtnManager.vue';
import GallerySlider from './components/GallerySlider.vue';

import logo from '@/assets/images/logo.svg?url'
import imgAmy from '@/assets/images/image-amy.webp'

export default {
  data() {
    return {
      logo,
      imgAmy,
      isTrue: false,
    }
  },
  components: {
    NavManager,
    MainGrid,
    BtnManager,
    GallerySlider,
  }
}
</script>
<template>
  <body class=" flex flex-col items-center bg-neo-transparent text-neo-black font-jakarta">
    <header
      class=" flex flex-col gap-8 TB:gap-16 w-full max-w-[425px] TB:max-w-[1024px] DT:max-w-[1920px] mb-8 TB:mb-16 DT:mb-20 pt-4 TB:pt-9">
      <nav class=" flex justify-between items-center px-4 TB:px-10 DT:px-[165px]">
        <NavManager />
      </nav>
      <div class=" flex flex-col gap-4 TB:gap-7 DT:gap-6 px-4 TB:px-10 DT:px-[300px] text-center">
        <h1
          class=" text-[36px] TB:text-[2.75rem] DT:text-[3.5rem] leading-[45px] TB:leading-[3.375rem] DT:leading-[4.375rem] font-bold">
          Design solutions made
          easy</h1>
        <p
          class=" TB:px-12 DT:px-16 text-neo-gray text-[16px] TB:text-[1.125rem] leading-[26px] TB:leading-[1.75rem] font-medium">
          With over ten years of experience in various design disciplines, I’m your one-stop shop for your design needs.
        </p>
      </div>
    </header>
    <main
      class=" flex flex-col gap-[6.25rem] TB:gap-[7.5rem] DT:gap-0 w-full max-w-[425px] TB:max-w-[1024px] DT:max-w-[1920px] mb-10 TB:mb-14">
      <section class=" grid grid-cols-2 TB:grid-cols-4 DT:grid-cols-6 gap-6 DT:mb-[8.5rem] px-4 TB:px-10 DT:px-[165px]">
        <MainGrid v-for="index in 6" :data-index="index - 1" />
      </section>
      <section
        class=" flex flex-col TB:flex-row DT:items-center gap-10 TB:gap-[69px] DT:gap-[125px] DT:mb-[5.5rem] px-4 TB:px-10 DT:px-[165px]">
        <img class=" TB:h-[364px] DT:h-[445px] TB:-ml-[84px] DT:ml-0 px-6 TB:p-0 select-none" :src="imgAmy" alt="imgAmy"
          draggable="false">
        <div class=" flex flex-col items-center TB:items-start gap-6 DT:gap-9">
          <div class=" flex flex-col gap-6 DT:gap-8 text-center TB:text-start">
            <h2
              class=" text-[26px] TB:text-[2rem] DT:text-[2.5rem] leading-[33px] TB:leading-[2.5rem] DT:leading-[3.125rem] font-bold">
              I’m Amy, and I’d love to work on your next project</h2>
            <p class=" text-neo-gray text-[16px] TB:text-[1.125rem] leading-[26px] TB:leading-[1.75rem] font-medium">
              I love working with others to create beautiful design solutions. I’ve designed everything from brand
              illustrations
              to complete mobile apps. I’m also handy with a camera!
            </p>
          </div>
          <BtnManager :isMain="true" />
        </div>
      </section>
      <section class=" DT:mb-[5.5rem]">
        <GallerySlider />
      </section>
      <section class=" px-4 TB:px-10 DT:px-[165px]">
        <article
          class=" flex flex-col DT:flex-row items-center DT:justify-between gap-6 TB:gap-7 px-6 TB:px-[72px] DT:px-16 py-12 TB:py-14 DT:py-20 bg-neo-black text-neo-transparent rounded-[10px]">
          <div class=" flex flex-col gap-6 TB:gap-7 DT:gap-6 DT:w-[55%] text-center DT:text-left">
            <h2
              class=" text-[26px] TB:text-[32px] DT:text-[2.5rem] leading-[33px] TB:leading-[40px] DT:leading-[3.125rem] font-bold">
              Book a call with me</h2>
            <p class=" text-[16px] TB:text-[1.125rem] leading-[1.625rem] TB:leading-[1.75rem] font-medium">
              I’d love to have a chat to see how I can help you. The best first step is for us to discuss your project
              during a free consultation. Then we can move forward from there.
            </p>
          </div>
          <BtnManager class=" DT:mr-8" :is-main="true" />
        </article>
      </section>
    </main>
    <footer
      class=" flex justify-between items-center w-full max-w-[425px] TB:max-w-[1024px] DT:max-w-[1920px] px-4 TB:px-10 DT:px-[165px] pb-8 TB:pb-14 DT:pb-16">
      <NavManager />
    </footer>
  </body>
</template>