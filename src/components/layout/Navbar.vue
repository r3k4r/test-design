<script setup lang="ts">
import { computed, ref } from 'vue'
import { useRoute } from 'vue-router'
import Button from '../ui/Button.vue'
import { Menu } from 'lucide-vue-next'
import Logo from '../brand/Logo.vue'

const route = useRoute()
const isMenuOpen = ref(false)
const links = [
  { name: 'Home', path: '/' },
  { name: 'About us', path: '/about' },
  { name: 'FAQs', path: '/faqs' },
  { name: 'Contact us', path: '/contact' },
]
const isActive = computed(() => {
  return (linkPath: string) => linkPath === route.path
})

const menuHandler = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <div class="flex justify-between items-center container-layout-lg padding-layout mt-[46px] h-16">
    <div class="z-110">
      <Logo />
    </div>

    <nav class="hidden lg:flex gap-12 items-center">
      <router-link
        v-for="link in links"
        :key="link.name"
        :to="link.path"
        :class="`font-semibold ${isActive(link.path) ? 'text-primary' : 'text-muted'}`"
      >
        {{ link.name }}
      </router-link>
    </nav>

    <div class="flex gap-4 items-center">
      <Button variant="secondary" class="hidden lg:block">Register</Button>
      <Button>Login</Button>
      <Menu class="lg:hidden cursor-pointer z-110" @click="menuHandler" :size="30" />
    </div>

    <div
      v-show="isMenuOpen"
      class="fixed inset-0 lg:hidden bg-white z-100 flex flex-col items-center justify-center padding-layout"
    >
      <nav class="w-full text-center flex items-center flex-col justify-center pb-24 gap-y-12">
        <router-link
          v-for="link in links"
          :key="link.name + '-overlay'"
          :to="link.path"
          :class="`text-2xl ${isActive(link.path) ? 'text-primary' : 'text-gray-500'}`"
          @click="menuHandler"
        >
          {{ link.name }}
        </router-link>
        <a
          href=""
          class="text-xl w-full flex items-center justify-center px-6 max-w-sm h-12 font-semibold rounded-full border border-black/40 hover:text-muted-foreground hover:bg-muted transition-all"
          >Register
        </a>
      </nav>
    </div>
  </div>
</template>
