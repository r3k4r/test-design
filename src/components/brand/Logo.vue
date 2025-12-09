<script setup lang="ts">
interface Props {
  class?: string
}

const props = withDefaults(defineProps<Props>(), {
  class: '',
})
</script>

<template>
  <router-link to="/" class="cursor-pointer">
    <img src="/logo.svg" alt="logo" :class="props.class" />
  </router-link>
</template>
