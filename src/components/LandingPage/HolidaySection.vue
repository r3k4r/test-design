<script setup lang="ts">
import left from '@/assets/left-frame.svg'
import right from '@/assets/right-frame.svg'
import image1 from '@/assets/image-1.png'
import image2 from '@/assets/image-2.png'
import image3 from '@/assets/image-3.png'
import image4 from '@/assets/image-4.png'
import { motion } from 'motion-v'

const cardItems = [
  {
    title: 'Hotels',
    desc: 'Easily browse and book from a global inventory of hotels with real-time availability and competitive rates. We connect you to trusted suppliers, making hotel bookings faster and more reliable.',
    image: image1,
  },
  {
    title: 'Packages',
    desc: 'Create and sell customized travel packages effortlessly. Combine flights, hotels, transfers, and activities into one seamless offer tailored to your client’s needs — all in just a few clicks.',
    image: image2,
  },
  {
    title: 'Activities',
    desc: 'Discover and book unforgettable experiences around the world. From city tours to adventure excursions, offer your customers a wide variety of activities to enhance their travel plans.',
    image: image3,
  },
  {
    title: 'Transfer',
    desc: 'Simplify ground transportation with a wide range of reliable transfer services, from airport pickups to city-to-city rides. We offer private and shared transfers services through trusted partners.',
    image: image4,
  },
]
</script>

<template>
  <section class="mt-[130px] lg:mt-[368px] containerr w-full xl:px-10">
    <div
      class="w-full lg:pb-0 pb-6 pt-[110px] max-w-[1653px] h-fit xl:max-h-[738px] xl:rounded-3xl px-4 bg-primary relative overflow-hidden"
    >
      <div class="flex flex-col items-center justify-center">
        <!-- TITLE AND SUBTITLE -->
        <div class="flex flex-col items-center z-20 justify-center gap-6 max-w-[900px]">
          <h1 class="leading-[150%] text-[48px] font-bold lg:text-center">
            All Your Holidays Needs In One Place
          </h1>
          <p class="leading-[150%] lg:text-center">
            Whether you're planning a luxury getaway, a business trip, or a group tour, Babylon
            Holiday provides the tools you need to deliver exceptional travel solutions to your
            clients—anytime, anywhere
          </p>
        </div>

        <!-- CARDS -->
        <div
          class="mt-auto max-w-344 pt-14 lg:pt-24 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 items-end justify-center gap-6"
        >
          <motion.div
            :initial="{ y: 0, borderBottomLeftRadius: 0, borderBottomRightRadius: 0 }"
            :whileHover="{ y: -16, borderBottomLeftRadius: 8, borderBottomRightRadius: 8 }"
            :transition="{ duration: 0.5, ease: 'easeInOut' }"
            v-for="(item, index) in cardItems"
            :key="index"
            class="bg-white rounded-lg lg:rounded-b-none h-full p-6 pb-0 lg:pr-0 group flex flex-col gap-4"
          >
            <!-- TITLE -->
            <div class="pr-6">
              <h1 class="text-[20px] font-medium leading-[150%]">{{ item.title }}</h1>
              <p class="text-[14px] leading-[150%]">{{ item.desc }}</p>
            </div>
            <!-- IMAGE -->
            <div class="p-4 lg:pr-0 pb-0 pt-4 rounded-lg rounded-b-none bg-[#f3f3f3]">
              <img :src="item.image" alt="" />
            </div>
          </motion.div>
        </div>
      </div>
      <!-- LEFT & RIGHT FRAME -->
      <div class="absolute z-10 hidden md:block -top-48 left-4">
        <img :src="left" alt="Left Frame" />
      </div>
      <div class="absolute z-10 hidden md:block -top-32 right-4">
        <img :src="right" alt="Right Frame" />
      </div>
    </div>
  </section>
</template>
