<script setup lang="ts">
import Button from '../ui/Button.vue'
import { motion } from 'motion-v'

const floatingAnimation = {
  initial: { y: 0, scale: 1, boxShadow: '0 1px 2px rgba(0, 0, 0, 0.1)' },
  animate: {
    y: [-20, 0, -20],
    scale: [0.95, 1, 0.95],
    boxShadow: [
      '0 8px 16px rgba(0, 0, 0, 0.18)',
      '0 1px 2px rgba(0, 0, 0, 0.1)',
      '0 8px 16px rgba(0, 0, 0, 0.18)',
    ],
  },
  transition: {
    duration: 4,
    repeat: Infinity,
  },
}

const floatingAnimation2 = {
  initial: { y: 0, scale: 1, boxShadow: '0 1px 2px rgba(0, 0, 0, 0.1)' },
  animate: {
    y: [-15, 0, -15],
    scale: [0.96, 1, 0.96],
    boxShadow: [
      '0 7px 14px rgba(0, 0, 0, 0.16)',
      '0 1px 2px rgba(0, 0, 0, 0.1)',
      '0 7px 14px rgba(0, 0, 0, 0.16)',
    ],
  },
  transition: {
    duration: 3.5,
    repeat: Infinity,
    delay: 0.5,
  },
}

const floatingAnimation3 = {
  initial: { y: 0, scale: 1, boxShadow: '0 1px 2px rgba(0, 0, 0, 0.1)' },
  animate: {
    y: [-18, 0, -18],
    scale: [0.94, 1, 0.94],
    boxShadow: [
      '0 10px 18px rgba(0, 0, 0, 0.2)',
      '0 1px 2px rgba(0, 0, 0, 0.1)',
      '0 10px 18px rgba(0, 0, 0, 0.2)',
    ],
  },
  transition: {
    duration: 4.2,
    repeat: Infinity,
    delay: 1,
  },
}
</script>

<template>
  <section
    class="mt-[125px] md:mt-[343px] max-w-[1102px] w-full padding relative h-full min-h-[946px] flex items-center justify-center"
  >
    <div
      class="w-[250px] border border-gray-400/20 bg-transparent aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%]"
    />
    <div
      class="w-[100px] border border-gray-400/20 bg-transparent aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%]"
    />
    <div
      class="w-[375px] border border-gray-400/20 bg-transparent aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%]"
    />
    <div
      class="w-[550px] border border-gray-400/20 bg-transparent aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%]"
    />
    <div
      class="w-[725px] border border-gray-400/20 bg-transparent aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%]"
    />

    <div
      class="w-[350px] aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%] bg-primary/5 blur-[30px]"
    />

    <div class="relative flex flex-col items-center justify-center">
      <div class="flex items-center justify-between gap-5 flex-wrap sm:flex-nowrap w-full mb-12">
        <motion.div
          :initial="floatingAnimation.initial"
          :animate="floatingAnimation.animate"
          :transition="floatingAnimation.transition"
          class="w-fit min-h-14 px-3 bg-white border border-[#DDDDDD] rounded-full flex items-center justify-start flex-nowrap gap-2 -translate-x-14 -translate-y-8"
        >
          <div class="w-9 h-9 bg-primary aspect-square rounded-full" />
          <div class="flex flex-col items-start justify-start">
            <h1 class="text-sm font-medium leading-[112%]">+20</h1>
            <p class="text-sm font-medium leading-[112%]">Bed bank suppliers</p>
          </div>
        </motion.div>
        <motion.div
          :initial="floatingAnimation2.initial"
          :animate="floatingAnimation2.animate"
          :transition="floatingAnimation2.transition"
          class="w-fit min-h-14 px-3 bg-white border border-[#DDDDDD] rounded-full flex items-center justify-start flex-nowrap gap-2"
        >
          <div class="w-9 h-9 bg-primary aspect-square rounded-full" />
          <div class="flex flex-col items-start justify-start">
            <h1 class="text-sm font-medium leading-[112%]">+190</h1>
            <p class="text-sm font-medium leading-[112%]">Countries</p>
          </div>
        </motion.div>
        <motion.div
          :initial="floatingAnimation3.initial"
          :animate="floatingAnimation3.animate"
          :transition="floatingAnimation3.transition"
          class="w-fit min-h-14 px-3 bg-white border border-[#DDDDDD] rounded-full flex items-center justify-start flex-nowrap gap-2 translate-x-14 -translate-y-20"
        >
          <div class="w-9 h-9 bg-primary aspect-square rounded-full" />
          <div class="flex flex-col items-start justify-start">
            <h1 class="text-sm font-medium leading-[112%]">+2.5M</h1>
            <p class="text-sm font-medium leading-[112%]">Hotel partners</p>
          </div>
        </motion.div>
      </div>
      <div class="flex flex-col items-center justify-center gap-12">
        <h1
          class="text-[40px] sm:text-5xl md:text-[54px] font-semibold max-w-[600px] text-center leading-[112%]"
        >
          Elevate your business to new levels
        </h1>
        <Button class="rounded-full! px-8">Learn more</Button>
      </div>
      <div class="flex items-center justify-between gap-5 flex-wrap sm:flex-nowrap w-full mt-12">
        <motion.div
          :initial="floatingAnimation2.initial"
          :animate="floatingAnimation2.animate"
          :transition="floatingAnimation2.transition"
          class="w-fit min-h-14 px-3 bg-white border border-[#DDDDDD] rounded-full flex items-center justify-start flex-nowrap gap-2 -translate-x-10 -translate-y-10"
        >
          <div class="w-9 h-9 bg-primary aspect-square rounded-full" />
          <div class="flex flex-col items-start justify-start">
            <h1 class="text-sm font-medium leading-[112%]">24/7/365</h1>
            <p class="text-sm font-medium leading-[112%]">Support</p>
          </div>
        </motion.div>
        <motion.div
          :initial="floatingAnimation3.initial"
          :animate="floatingAnimation3.animate"
          :transition="floatingAnimation3.transition"
          class="w-fit min-h-14 px-3 bg-white border border-[#DDDDDD] rounded-full flex items-center justify-start flex-nowrap gap-2 translate-x-4 translate-y-[82px]"
        >
          <div class="w-9 h-9 bg-primary aspect-square rounded-full" />
          <div class="flex flex-col items-start justify-start">
            <h1 class="text-sm font-medium leading-[112%]">+100</h1>
            <p class="text-sm font-medium leading-[112%]">Helpdesk staff</p>
          </div>
        </motion.div>
        <motion.div
          :initial="floatingAnimation.initial"
          :animate="floatingAnimation.animate"
          :transition="floatingAnimation.transition"
          class="w-fit min-h-14 px-3 bg-white border border-[#DDDDDD] rounded-full flex items-center justify-start flex-nowrap gap-2 translate-x-[82px] -translate-y-10"
        >
          <div class="w-9 h-9 bg-primary aspect-square rounded-full" />
          <div class="flex flex-col items-start justify-start">
            <h1 class="text-sm font-medium leading-[112%]">+1000</h1>
            <p class="text-sm font-medium leading-[112%]">Direct hotel contacts</p>
          </div>
        </motion.div>
      </div>
    </div>
  </section>
</template>
