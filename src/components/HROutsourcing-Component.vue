<template>
  <div class="body bg-gradient-to-b from-[var(--background)] to-white">
    <div class="flex items-center flex-col">
      <h1 class="heading">RETAINER MODEL</h1>
      <p class="subheading text-secondary">
        Consistent excellence, predictable investment, exceptional value
      </p>
      <div class="flex items-center justify-center gap-20">
        <div class="flex items-center justify-center">
          <div>
          <h1 class="text-3xl font-semibold text-secondary">What are</h1>
          <h1 class="text-4xl font-semibold text-secondary">RETAINERS ?</h1>
          <p class="pt-4 pb-6 max-w-[600px]">These are upfront payment fees to secure services over long term. Fees are deducted monthly from the retainer so clients do not need to make monthly payments.</p>
          <span class="btn bg-secondary">Message Us</span>
          </div>
        </div>
        <div class="flex flex-col items-center justify-center mt-10">
          <h1 class="text-3xl font-semibold text-secondary mb-2">BENEFITS</h1>
          <Carousel/>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import Carousel from '../components/miniComponents/Benefits-Carousel.vue'
</script>

<style lang="scss" scoped></style>
