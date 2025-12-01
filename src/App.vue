<script setup lang="ts">
import Navbar from './components/layout/Navbar.vue'
</script>

<template>
  <div class="flex flex-col items-center justify-center">
    <Navbar />
    <router-view />
  </div>
</template>
