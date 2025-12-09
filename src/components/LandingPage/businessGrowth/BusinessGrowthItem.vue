<script setup lang="ts">
import type { number } from 'motion-v'
import { twMerge } from 'tailwind-merge'
import { computed } from 'vue'

type props = {
  class?: string
  delay?: number
  number?: string
  description?: string
}

const props = withDefaults(defineProps<props>(), {
  class: '',
  delay: 0,
})

const divClasses = computed(() => {
  const baseClasses =
    'animate w-fit min-h-10 sm:min-h-14 px-2 sm:px-3 bg-white border border-[#DDDDDD] letter-spacing-normal rounded-full flex items-center justify-start flex-nowrap gap-1 sm:gap-2'
  return twMerge(baseClasses, props.class)
})
</script>

<template>
  <div :class="divClasses" :style="{ animationDelay: props.delay + 'ms' }">
    <div class="w-6 h-6 sm:w-8 sm:h-8 md:w-9 md:h-9 bg-primary aspect-square rounded-full" />
    <div class="flex flex-col items-start justify-start">
      <h1 class="text-xs sm:text-sm font-medium leading-[112%]">{{ props.number }}</h1>
      <p class="text-[10px] sm:text-sm font-medium leading-[112%]">{{ props.description }}</p>
    </div>
  </div>
</template>
