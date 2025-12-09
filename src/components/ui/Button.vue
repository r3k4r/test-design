<script setup lang="ts">
import { computed, useSlots } from 'vue'
import { twMerge } from 'tailwind-merge'

interface Props {
  variant?: 'primary' | 'secondary'
  class?: string
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'primary',
  class: '',
})

const buttonClasses = computed(() => {
  const baseClasses = 'justify-center items-center h-12 px-6 text-sm font-semibold rounded-lg'

  const variantClasses = {
    primary: 'bg-primary text-primary-foreground cursor-pointer',
    secondary: 'bg-secondary text-secondary-foreground cursor-pointer',
    muted: 'bg-muted text-muted-foreground cursor-pointer',
    destructive:
      'bg-destructive text-destructive-foreground hover:bg-destructive/90 cursor-pointer',
    accent: 'bg-accent text-accent-foreground hover:bg-accent/90 cursor-pointer',
    outline:
      'border border-input bg-background hover:bg-accent hover:text-accent-foreground cursor-pointer',
  }

  return twMerge(baseClasses, variantClasses[props.variant], props.class)
})
</script>

<template>
  <button :class="buttonClasses">
    <slot></slot>
  </button>
</template>
