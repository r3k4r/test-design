<script setup lang="ts">
import { ref } from 'vue'
import { Motion } from 'motion-v'
import right from '@/assets/frame.svg'
import { BadgeDollarSign, Calendar, Calendar1, Languages, Link, Settings } from 'lucide-vue-next'

const navItems = [
  {
    icon: Calendar,
    title: 'Booking Management',
  },
  {
    icon: Calendar1,
    title: 'Reservation Insights',
  },
  {
    icon: BadgeDollarSign,
    title: 'Financial Records',
  },
  {
    icon: Link,
    title: 'Agent & Staff Management',
  },
  {
    icon: Languages,
    title: 'Multi-Language Support',
  },
  {
    icon: Settings,
    title: 'Customizable Markups',
  },
]

const itemContent = [
  {
    icon: Calendar,
    title: 'Booking Management',
    description:
      'Easily search, compare, and book hotels, tours, and holiday packages across thousands of destinations. Modify or cancel reservations, track booking status in real time, and manage client requests—all from a single, intuitive dashboard. Simplify the booking process for both you and your clients, enhancing efficiency and customer satisfaction.',
  },
  {
    icon: Calendar1,
    title: 'Reservation Insights',
    description:
      'Stay ahead with powerful analytics and reporting tools. View trends, monitor top-selling destinations, and access detailed booking histories. Use these insights to better understand your clients’ preferences, optimize booking strategies, and boost your sales performance. Make informed decisions based on real-time data.',
  },
  {
    icon: BadgeDollarSign,
    title: 'Financial Records',
    description:
      'Keep your finances organized with transparent billing, downloadable invoices, and full payment history. Monitor your credit limits, reconcile payments, and generate financial reports with just a few clicks. Maintain accurate financial records, helping you streamline accounting and improve cash flow management.',
  },
  {
    icon: Link,
    title: 'Agent & Staff Management',
    description:
      'Assign roles, control permissions, and track performance across your team. Babylon Holiday allows you to manage multiple agents under your account with full visibility and control. Improve team coordination, ensure productivity, and optimize performance management with easy-to-use tools.',
  },
  {
    icon: Languages,
    title: 'Multi-Language Support',
    description:
      'Cater to clients around the world with built-in support for multiple currencies and languages. Make your global operations smooth and user-friendly. Provide a seamless experience to international clients, improving customer satisfaction and expanding your reach to new markets.',
  },
  {
    icon: Settings,
    title: 'Customizable Markups',
    description:
      'Control your profits by setting custom markups, commissions, and discounts per supplier, destination, or partner. Tailor your pricing strategy based on your business goals. Ensure that your pricing model is flexible and optimized for maximum revenue generation and profitability.',
  },
]

const activeIndex = ref(0)

const setActiveItem = (index: number) => {
  activeIndex.value = index
}
</script>

<template>
  <section class="mt-[125px] lg:mt-[237px] containerr w-full xl:px-10">
    <div
      class="flex flex-col items-start justify-start gap-14 lg:gap-12 w-full max-w-[1664px] h-fit xl:max-h-[932px] xl:rounded-2xl p-6 lg:p-16 bg-[#1E1E1E] text-white relative overflow-hidden"
    >
      <div class="w-full max-w-[1471px] flex flex-col gap-16 items-start justify-start z-20">
        <h1 class="text-[36px] lg:text-[64px] font-semibold">
          Everything You Need to Manage, Seamlessly Covered In Babylon Holiday
        </h1>
        <!-- HEADER (NAVBAR) -->
        <div
          class="flex flex-col sm:flex-row flex-wrap items-start justify-start w-full sm:w-fit max-w-[1471px] gap-6 bg-[#303030] rounded-lg md:rounded-[28px] p-2 relative"
        >
          <div
            v-for="(item, index) in navItems"
            :key="item.title"
            @click="setActiveItem(index)"
            :class="`group cursor-pointer flex items-center justify-center gap-2 p-1.5 rounded-full transition-colors ${activeIndex === index ? 'bg-white' : 'hover:bg-white/10'}`"
          >
            <component
              :is="item.icon"
              :class="`p-2 w-[34px] h-[34px] transition-colors ${activeIndex === index ? 'bg-primary text-white rounded-full' : 'text-white rounded-full'}`"
            />
            <h4
              :class="`font-semibold transition-colors ${activeIndex === index ? 'text-black' : 'text-white'}`"
            >
              {{ item.title }}
            </h4>
          </div>
        </div>
      </div>

      <!-- CONTENT -->
      <div class="w-full z-20">
        <div class="flex flex-col gap-6">
          <!-- ICON -->
          <div
            class="w-[63px] h-[63px] flex items-center justify-center rounded-lg md:rounded-full aspect-square border border-gray-400/50"
          >
            <Motion
              :key="activeIndex"
              :initial="{ scale: 0.5, opacity: 0 }"
              :animate="{ scale: 1, opacity: 1 }"
              :transition="{ duration: 0.3, ease: 'easeOut' }"
            >
              <component :is="itemContent[activeIndex]?.icon" class="w-8 h-8 text-white" />
            </Motion>
          </div>
          <!-- TITLE -->
          <Motion
            :key="`title-${activeIndex}`"
            :initial="{ x: 600, opacity: 0 }"
            :animate="{ x: 0, opacity: 1 }"
            :exit="{ x: -600, opacity: 0 }"
            :transition="{ duration: 0.4, ease: 'easeInOut' }"
          >
            <h1 class="text-[64px] leading-[112%] font-semibold">
              {{ itemContent[activeIndex]?.title }}
            </h1>
          </Motion>

          <!-- DESCRIPTION -->
          <Motion
            :key="`desc-${activeIndex}`"
            :initial="{ x: 600, opacity: 0 }"
            :animate="{ x: 0, opacity: 1 }"
            :exit="{ x: -100, opacity: 0 }"
            :transition="{ duration: 0.4, ease: 'easeInOut', delay: 0.1 }"
          >
            <p class="text-sm font-semibold text-white/60 max-w-[657px]">
              {{ itemContent[activeIndex]?.description }}
            </p>
          </Motion>
        </div>
      </div>

      <div class="absolute z-10 hidden md:block -top-20 -right-[150px]">
        <img :src="right" alt="Right Frame" />
      </div>
    </div>
  </section>
</template>
