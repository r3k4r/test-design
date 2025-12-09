<script setup lang="ts">
import Hero from '@/components/LandingPage/Hero.vue'
import ImageSection from '@/components/LandingPage/ImageSection.vue'
import FeaturesHighlight from '@/components/LandingPage/FeaturesHighlight.vue'
import ServicesOverview from '@/components/LandingPage/ServicesOverview.vue'
import WhyChooseUs from '@/components/LandingPage/WhyChooseUs.vue'
import PlatformCapabilities from '@/components/LandingPage/PlatformCapabilities.vue'
import InfiniteOpportunities from '@/components/LandingPage/InfiniteOpportunities.vue'
import BusinessGrowthCTA from '@/components/LandingPage/BusinessGrowthCTA.vue'
</script>

<template>
  <Hero />
  <ImageSection />
  <FeaturesHighlight />
  <ServicesOverview />
  <div class="w-full flex items-center justify-center bg-primary/5">
    <WhyChooseUs />
  </div>
  <BusinessGrowthCTA />
  <PlatformCapabilities />
  <InfiniteOpportunities />
</template>
