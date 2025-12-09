<script setup lang="ts">
import { ChartPie, Clock, FileChartLine, Sparkles } from 'lucide-vue-next'

const items = [
  {
    icon: ChartPie,
    title: 'Grow your business revenue',
  },
  {
    icon: Clock,
    title: 'Advance your booking methodology',
  },
  {
    icon: FileChartLine,
    title: 'Streamline your operations',
  },
  {
    icon: Sparkles,
    title: 'Delight your customers',
  },
]
</script>

<template>
  <section class="mt-[124px] lg:mt-52 container-layout-md w-full padding-layout">
    <!-- TEXT -->
    <div class="w-full flex flex-col items-start justify-start gap-12">
      <h1 class="text-start max-w-[535px] text-[40px] font-semibold leading-[134%]">
        Infinite Opportunities. One Platform.
      </h1>

      <div class="w-full grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6 lg:gap-4">
        <div
          v-for="value in items"
          :key="value.title"
          class="flex items-center justify-start gap-4 max-w-[257px] w-fit"
        >
          <div class="w-12 h-12 p-4 text-white bg-primary rounded-lg grid place-content-center">
            <component :is="value.icon" class="w-6 h-6" />
          </div>
          <p class="font-semibold">{{ value.title }}</p>
        </div>
      </div>
    </div>
  </section>
</template>
