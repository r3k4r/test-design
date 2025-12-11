<script setup lang="ts">
import { BellRing, BriefcaseBusiness, Radio, Shield } from 'lucide-vue-next'
import background from '/shapes/yellow-background.svg'

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
  <section class="mt-28 container-layout-md w-full padding-layout relative">
    <div class="grid grid-cols-2 gap-6 md:gap-6 md:gap-y-8">
      <div
        v-for="(item, index) in cardItems"
        :key="index"
        class="p-4 md:p-6 flex flex-col md:flex-row gap-4 md:gap-6 bg-transparent border border-black/10 rounded-lg md:items-center z-50"
      >
        <div
          class="h-12 w-12 aspect-square bg-muted text-white rounded-lg grid place-content-center"
        >
          <component :is="item.icon" />
        </div>
        <h3 class="text-base font-semibold leading-[150%]">{{ item.title }}</h3>
      </div>
    </div>

    <img
      :src="background"
      alt="background"
      class="absolute z-20 lg:-translate-x-[1000px] -translate-x-[200px] -translate-y-[600px] lg:-translate-y-[800px] min-w-[1200px] lg:min-w-[2800px] max-h-[1500px] lg:max-h-[1705px]"
    />
  </section>
</template>
