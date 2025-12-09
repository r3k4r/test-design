<script setup lang="ts">
import GlobalCommunityCTA from '@/components/LandingPage/GlobalCommunityCTA.vue'
import Footer from './Footer.vue'
import Navbar from './Navbar.vue'
</script>

<template>
  <div class="flex flex-col items-center justify-center overflow-hidden">
    <Navbar />
    <slot />
    <GlobalCommunityCTA />
    <Footer />
  </div>
</template>
