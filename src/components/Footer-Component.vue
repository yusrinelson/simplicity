<script setup>
import logo from "../assets/images/logo.png";
import { EnvelopeIcon, PhoneIcon, MapPinIcon } from "@heroicons/vue/24/solid";
import { Icon } from "@iconify/vue";
</script>

<template>
  <div
    class="body flex flex-col md:flex-row justify-between items-start gap-8 md:gap-4 bg-gradient-to-t from-[var(--background)] to-white px-6 md:px-12 py-8"
  >
    <!-- Logo and Description -->
    <div class="w-full md:w-auto">
      <div class="mb-4">
        <img :src="logo" alt="logo" height="90" width="90" class="mx-auto md:mx-0" />
      </div>
      <p class="max-w-[300px] text-gray-800 text-center md:text-left mx-auto md:mx-0">
        Making life easier since 2022. For all your Administrative and HR worries.
      </p>
    </div>

    <!-- Contact Us -->
    <div class="w-full md:w-auto text-center md:text-left">
      <h4 class="font-semibold text-primary mb-4 text-lg">Contact Us</h4>
      <ul class="space-y-3">
        <li class="flex items-start gap-3 justify-center md:justify-start">
          <EnvelopeIcon class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5" />
          <a
            href="mailto:simplicityhroutsourcing@gmail.com"
            class="text-gray-800 hover:text-secondary transition-colors break-all text-sm md:text-base"
          >
            simplicityhroutsourcing@gmail.com
          </a>
        </li>
        <li class="flex items-start gap-3 justify-center md:justify-start">
          <PhoneIcon class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5" />
          <a
            href="tel:+27674622624"
            class="text-gray-800 hover:text-secondary transition-colors text-sm md:text-base"
          >
            +27 67 462 2624
          </a>
        </li>
        <li class="flex items-start gap-3 justify-center md:justify-start">
          <MapPinIcon class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5" />
          <span class="text-gray-800 text-sm md:text-base">Cape Town, Western Cape</span>
        </li>
      </ul>
    </div>

    <!-- Follow Us -->
    <div class="w-full md:w-auto flex flex-col items-center">
      <h4 class="font-semibold text-primary mb-4 text-lg">Follow Us</h4>
      <ul class="flex flex-row gap-6">
        <a
          href="https://instagram.com/simplicityhr_outsourcing"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Follow us on Instagram"
          class="group"
        >
          <li class="hover:scale-110 transition-transform cursor-pointer">
            <Icon
              icon="ri:instagram-fill"
              class="text-green-500 group-hover:text-secondary text-3xl md:text-2xl transition-colors"
            />
          </li>
        </a>
        <!-- <a
          href="https://facebook.com/simplicityhr"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Follow us on Facebook"
          class="group"
        >
          <li class="hover:scale-110 transition-transform cursor-pointer">
            <Icon
              icon="ri:facebook-fill"
              class="text-green-500 group-hover:text-secondary text-3xl md:text-2xl transition-colors"
            />
          </li>
        </a>

        <a
          href="https://linkedin.com/simplicityhr"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Follow us on Linkedin"
          class="group"
        >
          <li class="hover:scale-110 transition-transform cursor-pointer">
            <Icon
              icon="ri:linkedin-fill"
              class="text-green-500 group-hover:text-secondary text-3xl md:text-2xl transition-colors"
            />
          </li>
        </a> -->
      </ul>
    </div>
  </div>

  <!-- Copyright Section -->
  <div class="bg-background py-4 px-4">
    <p class="text-center text-sm font-semibold text-gray-800">
      &copy; 2025 Simplicity. All rights reserved.
    </p>
    <p class="text-center text-xs md:text-sm text-gray-500 mt-1">
      Designed & Developed by
      <a
        href="https://github.com/yusrinelson"
        target="_blank"
        rel="noopener noreferrer"
        class="hover:text-secondary transition-colors font-medium"
      >
        Yusri Nelson
      </a>
      |
      <a
        href="https://github.com/jacobdaniels30"
        target="_blank"
        rel="noopener noreferrer"
        class="hover:text-secondary transition-colors font-medium"
      >
        Jacob Daniels
      </a>
    </p>
  </div>
</template>

<style lang="scss" scoped></style>