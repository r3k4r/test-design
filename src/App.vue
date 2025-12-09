<script setup lang="ts">
import { Motion } from 'motion-v'
import Layout from './components/layout/Layout.vue'
import LandingAnimation from './components/animations/LandingAnimation.vue'
</script>

<template>
  <LandingAnimation />
  <Motion
    :initial="{ opacity: 0 }"
    :animate="{ opacity: 1 }"
    :transition="{ duration: 0.6, delay: 2.5, ease: 'easeOut' }"
  >
    <Layout>
      <router-view />
    </Layout>
  </Motion>
</template>
