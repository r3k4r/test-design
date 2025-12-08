<script setup lang="ts">
import { Mail, Phone, Linkedin, Facebook, Instagram } from 'lucide-vue-next'
import logo from '@/assets/logo.svg'
import Button from '../ui/Button.vue'

const year = new Date().getFullYear()
</script>

<template>
  <section
    class="w-full bg-[#F2F2F2] pt-[300px] sm:pt-[250px] z-10 flex items-center justify-center px-4 sm:px-6 lg:px-8"
  >
    <div class="w-full max-w-[1376px]">
      <!-- Header & Body Container -->
      <div class="flex flex-col gap-[62px]">
        <!-- Header -->
        <div
          class="w-full flex flex-col sm:flex-row items-start sm:items-center justify-between gap-6"
        >
          <!-- Logo -->
          <router-link to="/" class="shrink-0 w-[153px] h-[53px]">
            <img :src="logo" alt="Babylon Holiday Logo" class="h-12 sm:h-14 md:h-16 w-auto" />
          </router-link>

          <!-- Social Icons -->
          <div class="flex items-center gap-2">
            <a
              href="#"
              class="text-muted hover:text-[#0A66C2] duration-300 size-[41px] flex items-center justify-center"
            >
              <Linkedin :size="24" />
            </a>
            <a
              href="#"
              class="text-muted hover:text-[#1877F2] duration-300 size-[41px] flex items-center justify-center"
            >
              <Facebook :size="24" />
            </a>
            <a
              href="#"
              class="text-muted hover:text-[#E1306C] duration-300 size-[41px] flex items-center justify-center"
            >
              <Instagram :size="24" />
            </a>
          </div>
        </div>

        <!-- Body -->
        <div class="w-full flex flex-col lg:flex-row items-start justify-between gap-8 lg:gap-0">
          <div class="flex flex-col sm:flex-row gap-[72px] w-full items-start justify-between">
            <!-- Left Section - Contact Info -->
            <div class="w-full flex flex-col gap-4">
              <a href="mailto:info@babylonholiday.com" class="flex items-center gap-3 w-fit">
                <Mail :size="20" class="text-muted shrink-0" />
                <span class="text-sm font-semibold underline text-muted"
                  >info@babylonholiday.com</span
                >
              </a>
              <a href="tel:++9647735566009" class="flex items-center gap-3 w-fit">
                <Phone :size="20" class="text-muted shrink-0" />
                <span class="text-sm font-semibold underline text-muted">+964 773 556 6009</span>
              </a>
            </div>

            <!-- Right Section - Menu, Visit Us -->
            <div
              class="w-full flex items-start justify-start sm:justify-end lg:mr-[72px] gap-[72px]"
            >
              <!-- Menu -->
              <div class="flex flex-col gap-4">
                <h3 class="text-base sm:text-lg font-semibold text-muted">Menu</h3>
                <ul class="flex flex-col gap-3">
                  <li>
                    <router-link to="/about" class="text-sm font-semibold text-[#757575]"
                      >About Us</router-link
                    >
                  </li>
                  <li>
                    <router-link to="/contact" class="text-sm font-semibold text-[#757575]"
                      >Contact Us</router-link
                    >
                  </li>
                  <li>
                    <router-link to="/faqs" class="text-sm font-semibold text-[#757575]"
                      >FAQs</router-link
                    >
                  </li>
                </ul>
              </div>

              <!-- Visit Us -->
              <div class="flex flex-col gap-4">
                <h3 class="text-base sm:text-lg font-semibold text-muted">Visit Us</h3>
                <ul class="flex flex-col gap-3">
                  <li>
                    <router-link
                      to="/iraq?country=iraq"
                      class="text-sm font-semibold text-[#757575]"
                      >Iraq</router-link
                    >
                  </li>
                  <li>
                    <router-link
                      to="/germany?country=germany"
                      class="text-sm font-semibold text-[#757575]"
                      >Germany</router-link
                    >
                  </li>
                  <li>
                    <router-link to="/uae?country=uae" class="text-sm font-semibold text-[#757575]"
                      >UAE</router-link
                    >
                  </li>
                  <li>
                    <router-link
                      to="/turkey?country=turkey"
                      class="text-sm font-semibold text-[#757575]"
                      >Turkey</router-link
                    >
                  </li>
                </ul>
              </div>
            </div>
          </div>

          <!-- Newsletter -->
          <div class="flex flex-col gap-8 sm:col-span-2 lg:col-span-1">
            <div class="flex flex-col gap-4">
              <h3 class="text-base sm:text-lg font-semibold text-muted">Newsletter</h3>
              <p class="text-sm font-semibold text-[#757575] max-w-[352px]">
                Subscribe with our newsletter to receive latest updates
              </p>
            </div>
            <div class="flex flex-row gap-4 w-full">
              <input
                type="email"
                placeholder="Enter your email"
                class="flex-1 px-5 py-2.5 text-sm sm:text-base border border-[#D9D9D9] rounded-lg focus:outline-none"
              />
              <Button class="border border-black"> Subscribe </Button>
            </div>
          </div>
        </div>
      </div>

      <!-- Divider & Copyright -->
      <div class="mt-[58px] flex flex-col gap-6 pb-8">
        <div class="w-full h-px bg-gray-300"></div>
        <div class="w-full flex items-start sm:items-center justify-between gap-4">
          <p class="text-sm font-semibold text-[#757575]">
            Copyright {{ year }} All rights reserved
          </p>
          <div class="flex items-center gap-6">
            <a href="#" class="text-sm font-semibold text-[#757575]">Privacy & Policy</a>
            <a href="#" class="text-sm font-semibold text-[#757575]">Terms Of Use</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
