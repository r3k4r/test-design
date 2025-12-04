<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { Motion } from 'motion-v'
import Navbar from './components/layout/Navbar.vue'
import Gateway from './components/LandingPage/Gateway.vue'
import Footer from './components/layout/Footer.vue'

const showDiv = ref(true)

onMounted(() => {
  setTimeout(() => {
    showDiv.value = false
  }, 2500)
})
</script>

<template>
  <Motion
    v-if="showDiv"
    :initial="{ opacity: 1 }"
    :animate="{ opacity: 0 }"
    :transition="{ duration: 0.6, delay: 1.4, ease: 'easeInOut' }"
    class="fixed inset-0 bg-white z-50 flex items-center justify-center"
  >
    <Motion
      :initial="{ y: 0 }"
      :animate="{ y: '100vh' }"
      :transition="{ duration: 0.6, delay: 1.3, ease: 'easeInOut' }"
      class="fixed inset-0 bg-[#1E1E1E] flex items-center justify-center"
    >
      <Motion
        :initial="{ opacity: 0 }"
        :animate="{ opacity: 1 }"
        :transition="{ duration: 0.4, ease: 'easeOut' }"
      >
        <h1
          class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-semibold text-white text-center max-w-[90vw] md:max-w-[800px] leading-[120%] px-6"
        >
          Your Business Gateway to Global Travel Solutions
        </h1>
      </Motion>
    </Motion>
  </Motion>

  <Motion
    v-if="!showDiv"
    :initial="{ opacity: 0 }"
    :animate="{ opacity: 1 }"
    :transition="{ duration: 0.6, ease: 'easeOut' }"
    class="flex flex-col items-center justify-center"
  >
    <Navbar />
    <router-view />
    <Gateway />
    <Footer />
  </Motion>
</template>
