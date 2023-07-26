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
    <header class=" flex flex-col gap-8 w-full max-w-[425px] TB:max-w-[1024px] DT:max-w-[1920px] mb-8 pt-4">
      <nav class=" flex justify-between items-center px-4">
        <NavManager />
      </nav>
      <div class=" flex flex-col gap-4 px-4 text-center">
        <h1 class=" text-[36px] leading-[45px] font-bold">Design solutions made easy</h1>
        <p class=" text-neo-gray text-[16px] leading-[26px] font-medium">
          With over ten years of experience in various design disciplines, I’m your one-stop shop for your design needs.
        </p>
      </div>
    </header>
    <main class=" flex flex-col gap-24 w-full max-w-[425px] TB:max-w-[1024px] DT:max-w-[1920px] mb-10">
      <section class=" grid grid-cols-2 TB:grid-cols-4 DT:grid-cols-6 gap-6 px-4 TB:px-10 DT:px-[165px]">
        <MainGrid v-for="index in 6" :data-index="index - 1" />
      </section>
      <section class=" flex flex-col gap-10 px-4">
        <img class=" px-6 select-none" :src="imgAmy" alt="imgAmy" draggable="false">
        <div class=" flex flex-col items-center gap-6 text-center">
          <h2 class=" text-[26px] leading-[33px] font-bold">I’m Amy, and I’d love to work on your next project</h2>
          <p class=" text-neo-gray text-[16px] leading-[26px] font-medium">
            I love working with others to create beautiful design solutions. I’ve designed everything from brand
            illustrations
            to complete mobile apps. I’m also handy with a camera!
          </p>
          <BtnManager :isMain="true" />
        </div>
      </section>
      <section>
        <GallerySlider />
      </section>
      <section class=" px-4">
        <article class=" flex flex-col items-center gap-6 px-6 py-12 bg-neo-black text-neo-transparent rounded-[10px]">
          <div class=" flex flex-col gap-6 text-center">
            <h2 class=" text-[26px] leading-[33px] font-bold">
              Book a call with me</h2>
            <p class=" text-[16px] leading-[26px] font-medium">
              I’d love to have a chat to see how I can help you. The best first step is for us to discuss your project
              during a free consultation. Then we can move forward from there.
            </p>
          </div>
          <BtnManager :is-main="true" />
        </article>
      </section>
    </main>
    <footer
      class=" flex justify-between items-center w-full max-w-[425px] TB:max-w-[1024px] DT:max-w-[1920px] px-4 TB:px-10 DT:px-[165px] pb-8 TB:pb-14 DT:pb-16">
      <NavManager />
    </footer>
  </body>
</template>