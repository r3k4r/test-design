<script setup lang="ts">
import { BellRing, BriefcaseBusiness, Radio, Shield } from 'lucide-vue-next'

const cardItems = [
  {
    icon: Radio,
    title: 'Live Availability and Dynamic Pricing',
  },
  {
    icon: BriefcaseBusiness,
    title: 'Designed Exclusively for B2B Travel professionals',
  },
  {
    icon: Shield,
    title: 'Secure Booking & Payment Gateway Integration',
  },
  {
    icon: BellRing,
    title: 'Access to Global Hotel Inventory',
  },
]
</script>

<template>
  <section class="mt-[121px] max-w-[1102px] w-full padding">
    <div class="grid grid-cols-2 gap-6 md:gap-8">
      <div
        v-for="(item, index) in cardItems"
        :key="index"
        class="p-4 md:p-6 flex flex-col md:flex-row gap-4 md:gap-6 bg-transparent border border-black/10 rounded-lg items-start"
      >
        <div
          class="h-12 w-12 aspect-square bg-black text-white rounded-md grid place-content-center"
        >
          <component :is="item.icon" />
        </div>
        <h3 class="text-base font-semibold leading-[150%]">{{ item.title }}</h3>
      </div>
    </div>
  </section>
</template>
