<script setup lang="ts">
import Button from '../ui/Button.vue'
</script>

<template>
  <section
    class="mt-[120px] lg:mt-44 w-full h-full max-h-[280px] sm:max-h-[200px] padding flex flex-col items-center justify-between gap-16 lg:gap-[101px]"
  >
    <div
      class="w-full max-w-[1376px] h-full min-h-[488px] sm:min-h-[346px] flex flex-col sm:items-center justify-between sm:justify-center gap-12 px-6 py-12 sm:py-16 bg-[#1E1E1E] rounded-2xl sm:rounded-3xl z-20"
    >
      <!-- TEXT -->
      <div
        class="flex flex-col gap-4 items-start sm:items-center justify-center w-full max-w-[350px] sm:max-w-[689px]"
      >
        <h1
          class="text-[40px] sm:text-[36px] font-semibold text-white sm:text-center leading-[150%]"
        >
          Become a part of our global family
        </h1>
        <p class="text-base sm:text-center font-semibold text-white leading-[150%]">
          Join a growing network of travel professionals, agents, and partners from around the world
          who trust Babylon Holiday for their travel business needs.
        </p>
      </div>
      <!-- BUTTON -->
      <div class="flex flex-wrap sm:flex-nowrap w-full items-center justify-center gap-4">
        <Button class="sm:hidden w-full sm:w-[150px] bg-white" variant="secondary">
          Contact Us
        </Button>
        <Button class="w-full sm:w-[150px]"> Join Us </Button>
      </div>
    </div>
  </section>
</template>
