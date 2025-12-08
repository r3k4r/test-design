<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
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
const navItemRefs = ref<(HTMLElement | null)[]>([])
const slidingBgStyle = ref({
  left: '0px',
  top: '0px',
  width: '0px',
  height: '0px',
})

const setActiveItem = (index: number) => {
  activeIndex.value = index
  updateSlidingBackground(index)
}

const updateSlidingBackground = (index: number) => {
  const targetElement = navItemRefs.value[index]
  if (targetElement) {
    const parent = targetElement.parentElement
    if (parent) {
      const parentRect = parent.getBoundingClientRect()
      const targetRect = targetElement.getBoundingClientRect()
      slidingBgStyle.value = {
        left: `${targetRect.left - parentRect.left}px`,
        top: `${targetRect.top - parentRect.top}px`,
        width: `${targetRect.width}px`,
        height: `${targetRect.height}px`,
      }
    }
  }
}

const setNavRef = (el: any, index: number) => {
  if (el) {
    navItemRefs.value[index] = el
    if (index === 0 && slidingBgStyle.value.width === '0px') {
      // Initialize position on first mount
      setTimeout(() => updateSlidingBackground(0), 100)
    }
  }
}

// Handle window resize to recalculate position
const handleResize = () => {
  updateSlidingBackground(activeIndex.value)
}

onMounted(() => {
  window.addEventListener('resize', handleResize)
  // Initial calculation after mount
  setTimeout(() => updateSlidingBackground(0), 150)
})

onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
})
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
          <!-- Sliding white background - works on all screen sizes -->
          <div
            class="absolute bg-white rounded-full transition-all duration-300 ease-in-out pointer-events-none"
            :style="{
              left: slidingBgStyle.left,
              top: slidingBgStyle.top,
              width: slidingBgStyle.width,
              height: slidingBgStyle.height,
            }"
          />

          <div
            v-for="(item, index) in navItems"
            :key="item.title"
            :ref="(el) => setNavRef(el, index)"
            @click="setActiveItem(index)"
            class="group cursor-pointer flex items-center justify-center gap-2 p-1.5 rounded-full relative z-10 hover:opacity-80 transition-opacity"
          >
            <div class="relative w-[34px] h-[34px]">
              <Motion
                v-if="activeIndex === index"
                :key="`icon-bg-${index}`"
                :initial="{ scale: 0, opacity: 0 }"
                :animate="{ scale: 1, opacity: 1 }"
                :transition="{ duration: 0.3, ease: 'backOut', delay: 0.28 }"
                class="absolute inset-0 bg-primary rounded-full"
              />
              <component
                :is="item.icon"
                :class="`relative z-10 p-2 w-[34px] h-[34px] transition-colors ${activeIndex === index ? 'text-white' : 'text-white'}`"
              />
            </div>
            <h4
              :class="`font-semibold transition-colors duration-300 ${activeIndex === index ? 'text-muted' : 'text-white'}`"
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
