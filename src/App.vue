<script setup lang="ts">
import Navbar from './components/layout/Navbar.vue'
import Gateway from './components/LandingPage/Gateway.vue'
import Footer from './components/layout/Footer.vue'
</script>

<template>
  <div class="flex flex-col items-center justify-center">
    <Navbar />
    <router-view />
    <Gateway />
    <Footer />
  </div>
</template>
