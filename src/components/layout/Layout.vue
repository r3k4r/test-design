<script setup lang="ts">
import Gateway from '../LandingPage/Gateway.vue'
import Footer from './Footer.vue'
import Navbar from './Navbar.vue'
</script>

<template>
  <div class="flex flex-col items-center justify-center overflow-hidden">
    <Navbar />
    <slot />
    <Gateway />
    <Footer />
  </div>
</template>
