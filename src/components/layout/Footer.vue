<script setup lang="ts">
import Button from '../ui/Button.vue'
import Logo from '../brand/Logo.vue'
import { Icon } from '@iconify/vue'

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
          <Logo class="h-14" />

          <!-- Social Icons -->
          <div class="flex items-start sm:items-center gap-2">
            <a
              href="#"
              class="text-muted hover:text-[#0A66C2] duration-300 size-[41px] flex items-center justify-center"
            >
              <Icon icon="fa6-brands:linkedin-in" width="20" height="20" />
            </a>
            <a
              href="#"
              class="text-muted hover:text-[#1877F2] duration-300 size-[41px] flex items-center justify-center"
            >
              <Icon icon="fa6-brands:facebook-f" width="20" height="20" />
            </a>
            <a
              href="#"
              class="text-muted hover:text-[#E1306C] duration-300 size-[41px] flex items-center justify-center"
            >
              <Icon icon="fa6-brands:instagram" width="20" height="20" />
            </a>
          </div>
        </div>

        <!-- Body -->
        <div class="w-full flex flex-col lg:flex-row items-start justify-between gap-8 lg:gap-0">
          <div class="flex flex-col sm:flex-row gap-[72px] w-full items-start justify-between">
            <!-- Left Section - Contact Info -->
            <div class="w-full flex flex-col gap-4">
              <a href="mailto:info@babylonholiday.com" class="flex items-center gap-3 w-fit">
                <Icon icon="fluent:mail-28-filled" width="24" height="24" />
                <span class="text-sm font-semibold underline text-muted"
                  >info@babylonholiday.com</span
                >
              </a>
              <a href="tel:++9647735566009" class="flex items-center gap-3 w-fit">
                <Icon icon="fluent:call-20-filled" width="24" height="24" />
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
                  <li v-for="route in ['About Us', 'Contact Us', 'FAQs']" :key="route">
                    <router-link
                      :to="`/${route.toLowerCase().replace(/ /g, '-')}`"
                      class="text-sm font-semibold text-[#757575]"
                      >{{ route }}</router-link
                    >
                  </li>
                </ul>
              </div>

              <!-- Visit Us -->
              <div class="flex flex-col gap-4">
                <h3 class="text-base sm:text-lg font-semibold text-muted">Visit Us</h3>
                <ul class="flex flex-col gap-3">
                  <li v-for="country in ['Iraq', 'Germany', 'UAE', 'Turkey']" :key="country">
                    <router-link
                      :to="`/${country.toLowerCase()}?country=${country.toLowerCase()}`"
                      class="text-sm font-semibold text-[#757575]"
                      >{{ country }}</router-link
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
              <Button class="font-extralight text-muted text-sm"> Subscribe </Button>
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
