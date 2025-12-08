<script setup lang="ts">
import Button from '../ui/Button.vue'
</script>

<template>
  <section class="flex flex-col items-center justify-center gap-6 mt-[118px] padding">
    <div class="flex items-center gap-1 border border-black/15 rounded-full p-1 px-2">
      <p class="text-muted/80 font-semibold">Gain access to 2.5M Hotel Partners</p>
    </div>

    <div class="flex flex-col items-center text-center gap-8">
      <h1
        class="xl:text-7xl lg:text-5xl sm:text-4xl text-3xl font-semibold text-muted leading-[150%] max-w-6xl"
      >
        Your Gateway to Global Deals of Hotels and Holiday Services
      </h1>
      <p
        class="font-semibold text-base text-primary-foreground/85 max-w-[552px] mx-auto leading-[140%]"
      >
        Babylon Holiday is a powerful accommodation and holiday booking engine that empower travel
        companies and OTAs from all over the world with the best content, support, and technology.
      </p>
      <div class="flex flex-wrap sm:flex-nowrap w-full items-center justify-center gap-4">
        <Button class="w-full sm:w-[150px]" variant="secondary"> Contact Us </Button>
        <Button class="w-full sm:w-[150px]"> Join Us </Button>
      </div>
    </div>
  </section>
</template>
