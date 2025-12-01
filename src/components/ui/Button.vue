<script setup lang="ts">
import { computed, useSlots } from 'vue'

interface Props {
  variant?: 'primary' | 'secondary'
  class?: string
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'primary',
  class: '',
})

const slots = useSlots()
//you can ad icons, icon position, aspect ratio...
// const emit = defineEmits(['click'])

const buttonClasses = computed(() => {
  const baseClasses = 'justify-center items-center h-12 px-6 text-sm font-semibold rounded-lg'

  const variantClasses = {
    primary: 'bg-primary text-primary-foreground hover:bg-primary/90 cursor-pointer',
    secondary: 'bg-secondary text-secondary-foreground hover:bg-secondary/80 cursor-pointer',
    muted: 'bg-muted text-muted-foreground hover:bg-muted/80 cursor-pointer',
    destructive:
      'bg-destructive text-destructive-foreground hover:bg-destructive/90 cursor-pointer',
    accent: 'bg-accent text-accent-foreground hover:bg-accent/90 cursor-pointer',
    outline:
      'border border-input bg-background hover:bg-accent hover:text-accent-foreground cursor-pointer',
  }

  return `${baseClasses} ${variantClasses[props.variant]} ${props.class}`.trim()
})
</script>

<template>
  <button :class="buttonClasses">
    <slot></slot>
  </button>
</template>
