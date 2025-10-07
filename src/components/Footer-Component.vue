<script setup>
import logo from "../assets/images/logo.png";
import { EnvelopeIcon, PhoneIcon, MapPinIcon } from "@heroicons/vue/24/solid";
import { Icon } from "@iconify/vue";
// import { FacebookIcon, InstagramIcon, LinkedinIcon } from '@iconify/vue'
</script>

<template>
  <div
    class="body flex justify-between flex-wrap bg-gradient-to-t from-[var(--background)] to-white"
  >
    <div>
      <div class="ml-4">
        <img :src="logo" alt="logo" height="90" width="90" />
      </div>
      <p class="max-w-[300px] text-gray-800">
        Making life easier since 2022. For all your Administrative and HR worries.
      </p>
    </div>
    <div>
      <h4 class="font-semibold text-primary mb-4">Contact Us</h4>
      <ul>
        <li class="flex items-start gap-3">
          <EnvelopeIcon class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5" />
          <a
            href="mailto:simplicityhroutscourcing@gmail.com"
            class="text-gray-800 hover:text-secondary transition-colors break-all"
          >
            simplicityhroutscourcing@gmail.com
          </a>
        </li>
        <li class="flex items-start gap-3">
          <PhoneIcon class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5" />
          <a href="tel:+27674622624" class="text-gray-800 hover:text-secondary transition-colors">
            +27 067 462 2624
          </a>
        </li>
        <li class="flex items-start gap-3">
          <MapPinIcon class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5" />
          <span class="text-gray-800">Cape Town, Western Cape</span>
        </li>
      </ul>
    </div>
    <div class="flex flex-col items-center">
      <h4 class="font-semibold text-primary mb-4">Follow Us</h4>
      <ul class="flex flex-row gap-4">
        <a
          href="https://facebook.com/simplicityhr"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Follow us on Facebook"
        >
          <li class="hover:scale-110 cursor-pointer">
            <Icon icon="ri:facebook-fill" class="text-green-500 text-2xl transition-transform" />
          </li>
        </a>

        <a
          href="https://instagram.com/simplicityhr_outsourcing"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Follow us on Instagram"
        >
          <li class="hover:scale-110 cursor-pointer">
            <Icon icon="ri:instagram-fill" class="text-green-500 text-2xl transition-transform" />
          </li>
        </a>

        <a
          href="https://linkedin.com/simplicityhr"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Follow us on Linkedin"
        >
          <li class="hover:scale-110 cursor-pointer">
            <Icon icon="ri:linkedin-fill" class="text-green-500 text-2xl transition-transform" />
          </li>
        </a>
      </ul>
    </div>
  </div>
  <p class="text-center py-1 text-sm bg-background text-gray-800">
    &copy; 2025 Simplicity. All rights reserved.
    <span class="text-gray-500">Designed & Developed by Yusri Nelson | Jacob Daniels</span>
  </p>
</template>

<style lang="scss" scoped></style>
