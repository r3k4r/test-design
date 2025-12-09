<script setup lang="ts">
import Button from '@/components/ui/Button.vue'
import BusinessGrowthItem from './BusinessGrowthItem.vue'
</script>

<template>
  <section
    class="mt-[125px] md:mt-[343px] container-layout-md w-full padding-layout relative h-full min-h-[946px] flex items-center justify-center overflow-hidden"
  >
    <div
      v-for="size in [175, 350, 525, 700, 875]"
      :key="size"
      class="border border-gray-400/20 bg-transparent aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%]"
      :style="{ width: size + 'px' }"
    />
    <div
      class="w-[350px] aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%] bg-primary/5 blur-[30px]"
    />

    <div class="relative flex flex-col items-center justify-center">
      <div class="flex items-center justify-between gap-5 flex-wrap sm:flex-nowrap w-full mb-12">
        <BusinessGrowthItem
          class="-translate-x-2 sm:-translate-x-4 md:-translate-x-14 -translate-y-10 xs:-translate-y-4 sm:-translate-y-6 md:-translate-y-8"
          :delay="0"
          number="+20"
          description="Bed bank suppliers"
        />
        <BusinessGrowthItem number="+190" description="Countries" :delay="500" />
        <BusinessGrowthItem
          class="translate-x-[100px] xs:translate-x-2 sm:translate-x-2 md:translate-x-14 -translate-y-8 sm:-translate-y-14 md:-translate-y-20"
          :delay="1000"
          number="+2.5M"
          description="Hotel Partners"
        />
      </div>
      <div class="flex flex-col items-center justify-center gap-12">
        <h1
          class="xl:text-7xl lg:text-5xl sm:text-4xl text-3xl font-semibold text-muted max-w-3xl text-center leading-[112%] statistics-title"
        >
          Elevate your business to new levels
        </h1>
        <Button class="rounded-full! w-full px-6 h-12 max-w-40">Learn more</Button>
      </div>
      <div class="flex items-center justify-between gap-5 flex-wrap sm:flex-nowrap w-full mt-12">
        <BusinessGrowthItem
          class="-translate-x-2 sm:-translate-x-6 md:-translate-x-10 -translate-y-4 sm:-translate-y-6 md:-translate-y-10"
          :delay="300"
          number="24/7/365"
          description="Support"
        />
        <BusinessGrowthItem
          class="translate-x-1 sm:translate-x-2 md:translate-x-4 -translate-y-4 xs:translate-y-10 sm:translate-y-[60px] md:translate-y-[82px]"
          :delay="700"
          number="+100"
          description="HelpDesk staff"
        />
        <BusinessGrowthItem
          class="translate-x-[100px] xs:translate-x-0 sm:translate-x-2.5 md:translate-x-[82px] -translate-y-4 sm:-translate-y-6 md:-translate-y-10"
          :delay="1200"
          number="+1000"
          description="Direct hotel contacts"
        />
      </div>
    </div>
  </section>
</template>

<style scoped>
.animate {
  animation: animate 5s ease-in-out infinite;
  transform-style: preserve-3d;
  will-change: transform, box-shadow;
  backface-visibility: hidden;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

@keyframes animate {
  0%,
  100% {
    transform: translateY(0) scale(0.9) translateZ(0);
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.3);
  }
  50% {
    transform: translateY(-12px) scale(1) translateZ(0);
    box-shadow: -3.07833px 7.07833px 13.0783px 0px rgba(0, 0, 0, 0.14);
  }
}
</style>
