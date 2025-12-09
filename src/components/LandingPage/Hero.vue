<script setup lang="ts">
import Button from '../ui/Button.vue'
import { Icon } from '@iconify/vue'
</script>

<template>
  <section class="flex flex-col items-center justify-center mt-[85px] padding-layout">
    <div class="flex items-center gap-1 border border-black/15 rounded-full py-0.5 px-2.5">
      <Icon class="text-primary" icon="si:unlock-fill" width="24" height="24" />
      <p class="text-muted font-semibold">Gain access to 2.5M Hotel Partners</p>
    </div>

    <div class="flex flex-col items-center text-center gap-y-6 mt-4">
      <h1
        class="xl:text-7xl lg:text-5xl sm:text-4xl text-3xl font-semibold text-muted leading-[150%] max-w-6xl"
      >
        Your Gateway to Global Deals of Hotels and Holiday Services
      </h1>
      <p class="font-semibold text-base text-muted/85 max-w-3xl mx-auto leading-[150%]">
        Babylon Holiday is a powerful accommodation and holiday booking engine that empower travel
        companies and OTAs from all over the world with the best content, support, and technology.
      </p>
      <div class="flex flex-wrap sm:flex-nowrap w-full items-center justify-center gap-4">
        <Button class="h-12 px-6 max-w-40 w-full" variant="secondary"> Contact Us </Button>
        <Button class="h-12 px-6 max-w-40 w-full"> Join Us </Button>
      </div>
    </div>
  </section>
</template>
