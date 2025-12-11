<script setup lang="ts">
import { Globe, Headset, Tag, WandSparkles } from 'lucide-vue-next'

const cardItems = [
  { icon: WandSparkles, title: 'Simplicity', desc: 'User-friendly technology' },
  { icon: Tag, title: 'Deals', desc: 'Competitive local and international rates' },
  { icon: Headset, title: 'Support', desc: 'Real-time service availability' },
  { icon: Globe, title: 'Content', desc: 'Integration with world’s top suppliers' },
]
</script>

<template>
  <section
    class="mt-[124px] lg:mt-[286px] container-layout-md w-full padding-layout flex flex-col items-center justify-between gap-16 lg:gap-[101px] relative"
  >
    <!-- TEXT -->
    <div class="max-w-[680px] flex flex-col items-center justify-center gap-6">
      <h1 class="md:text-center text-[48px] font-semibold leading-[134%]">
        Why choose Babylon Holiday?
      </h1>
      <p class="md:text-center leading-[150%]">
        With access to a vast global inventory of hotels, tours, and holiday packages, Babylon
        Holiday empowers travel professionals with:
      </p>
    </div>

    <!-- CARD -->
    <div
      class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-6 sm:gap-4 lg:gap-10 xl:gap-[82px]"
    >
      <div
        class="flex flex-col gap-4 items-start md:items-center justify-center"
        v-for="item in cardItems"
        :key="item.title"
      >
        <!-- ICON -->
        <div
          class="lg:w-[74px] w-12 aspect-square bg-black text-white rounded-lg grid place-content-center"
        >
          <component :is="item.icon" />
        </div>
        <!-- TEXT -->
        <div class="flex flex-col items-start md:items-center justify-center gap-2 h-full">
          <h5 class="md:text-center text-start leading-[150%] font-bold">{{ item.title }}</h5>
          <p class="md:text-center text-start text-muted/60 font-semibold">
            {{ item.desc }}
          </p>
        </div>
      </div>
    </div>

    <svg
      xmlns="http://www.w3.org/2000/svg"
      width="1920"
      height="152"
      viewBox="0 0 1920 152"
      fill="none"
      class="rotate-180 translate-y-[140px]"
    >
      <path
        d="M960 0.0291206C588.018 2.39395 0 152 0 152H1920C1920 152 1347.22 -2.43259 960 0.0291206Z"
        fill="#FFFCF3"
      />
    </svg>
  </section>
</template>
