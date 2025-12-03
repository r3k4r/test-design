<script setup lang="ts">
import right from '@/assets/frame.svg'
import { BadgeDollarSign, Calendar, Calendar1, Languages, Link, Settings } from 'lucide-vue-next'

const items = [
  {
    icon: Calendar,
    title: 'Booking Management',
  },
  {
    icon: Calendar1,
    title: 'Reservation Insights',
  },
  {
    icon: BadgeDollarSign,
    title: 'Financial Records',
  },
  {
    icon: Link,
    title: 'Agent & Staff Management',
  },
  {
    icon: Languages,
    title: 'Multi-Language Support',
  },
  {
    icon: Settings,
    title: 'Customizable Markups',
  },
]
</script>

<template>
  <section class="mt-[125px] lg:mt-[237px] containerr w-full xl:px-10">
    <div
      class="flex flex-col items-start justify-start gap-14 lg:gap-12 w-full max-w-[1664px] h-fit xl:max-h-[932px] xl:rounded-2xl p-6 lg:p-16 bg-[#1E1E1E] text-white relative overflow-hidden"
    >
      <div class="w-full max-w-[1471px] flex flex-col gap-16 items-start justify-start z-20">
        <h1 class="text-[36px] lg:text-[64px] font-semibold">
          Everything You Need to Manage, Seamlessly Covered In Babylon Holiday
        </h1>
        <div
          class="flex flex-col sm:flex-row flex-wrap items-start justify-start w-full sm:w-fit max-w-[1471px] gap-6 bg-[#303030] rounded-lg md:rounded-[28px] p-2 relative"
        >
          <div
            v-for="value in items"
            :key="value.title"
            class="group cursor-pointer flex items-center justify-center gap-2 active:bg-white p-1.5 text-black rounded-full"
          >
            <component
              :is="value.icon"
              class="group-active:bg-primary text-white rounded-full p-2 w-[34px] h-[34px]"
            />
            <h4 class="font-semibold text-white group-active:text-black">
              {{ value.title }}
            </h4>
          </div>
        </div>
      </div>

      <div class="w-full max-w-[615px] z-20">
        <div class="flex flex-col gap-6">
          <!-- ICON -->
          <div
            class="w-[63px] h-[63px] flex items-center justify-center rounded-lg md:rounded-full aspect-square border border-gray-400/50"
          >
            <Link />
          </div>
          <!-- TITLE -->
          <div>
            <h1 class="text-[64px] leading-[112%] font-semibold">Reservation Insights</h1>
          </div>
          <!-- DESCRIPTION -->
          <div>
            <p class="text-sm font-semibold text-white/60">
              Effortlessly search, compare, and book hotels, tours, and holiday packages across
              thousands of destinations. Modify or cancel reservations, track booking status in real
              time, and manage client requests—all from a single, intuitive dashboard.
            </p>
          </div>
        </div>
      </div>

      <div class="absolute z-10 hidden md:block -top-20 -right-[150px]">
        <img :src="right" alt="Right Frame" />
      </div>
    </div>
  </section>
</template>
