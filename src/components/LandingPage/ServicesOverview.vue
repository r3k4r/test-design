<script setup lang="ts">
const cardItems = [
  {
    title: 'Hotels',
    desc: 'Easily browse and book from a global inventory of hotels with real-time availability and competitive rates. We connect you to trusted suppliers, making hotel bookings faster and more reliable.',
    image: '/ServiceOverviewImages/image-1.png',
  },
  {
    title: 'Packages',
    desc: 'Create and sell customized travel packages effortlessly. Combine flights, hotels, transfers, and activities into one seamless offer tailored to your client’s needs — all in just a few clicks.',
    image: '/ServiceOverviewImages/image-2.png',
  },
  {
    title: 'Activities',
    desc: 'Discover and book unforgettable experiences around the world. From city tours to adventure excursions, offer your customers a wide variety of activities to enhance their travel plans.',
    image: '/ServiceOverviewImages/image-3.png',
  },
  {
    title: 'Transfer',
    desc: 'Simplify ground transportation with a wide range of reliable transfer services, from airport pickups to city-to-city rides. We offer private and shared transfers services through trusted partners.',
    image: '/ServiceOverviewImages/image-4.png',
  },
]
</script>

<template>
  <section class="lg:mt-[180px] mt-28 container-layout-lg w-full xl:px-10 z-50">
    <div
      class="w-full lg:pb-0 pb-6 pt-[110px] max-w-[1653px] h-fit xl:max-h-[738px] xl:rounded-2xl px-4 bg-primary relative overflow-hidden"
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
          <div
            v-for="(item, index) in cardItems"
            :key="index"
            class="bg-white rounded-lg lg:rounded-b-none h-full p-6 pb-0 lg:pr-0 group flex flex-col gap-4 duration-500 hover:-translate-y-4 hover:rounded-b-lg"
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
          </div>
        </div>
      </div>
      <!-- LEFT & RIGHT FRAME -->
      <div class="absolute z-10 hidden md:block -top-48 left-4">
        <img src="/shapes/left-frame.svg" alt="Left Frame" />
      </div>
      <div class="absolute z-10 hidden md:block -top-32 right-4">
        <img src="/shapes/right-frame.svg" alt="Right Frame" />
      </div>
    </div>
  </section>
</template>
