<script setup lang="ts">
import { twMerge } from 'tailwind-merge'
import { computed } from 'vue'

interface Props {
  class?: string
}

const props = withDefaults(defineProps<Props>(), {
  class: '',
})

const logoClasses = computed(() => {
  const baseClasses = 'lg:h-16 h-12'

  return twMerge(baseClasses, props.class)
})
</script>

<template>
  <router-link to="/" class="cursor-pointer">
    <img src="/logo.svg" alt="logo" :class="logoClasses" />
  </router-link>
</template>
