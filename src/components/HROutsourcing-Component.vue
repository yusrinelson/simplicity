<script setup>
import Carousel from '../components/miniComponents/Benefits-Carousel.vue'

// Scroll to section function
const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId);
  if (element) {
    const offset = 100; // Offset for your fixed navbar
    const elementPosition = element.getBoundingClientRect().top;
    const offsetPosition = elementPosition + window.pageYOffset - offset;

    window.scrollTo({
      top: offsetPosition,
      behavior: "smooth",
    });
  }
};
</script>

<template>
  <div class="body bg-gradient-to-b from-[var(--background)] to-white">
    <div class="flex items-center flex-col">
      <h1 class="heading">RETAINER MODEL</h1>
      <p class="subheading text-secondary">
        Consistent excellence, predictable investment, exceptional value
      </p>
      <div class="flex flex-col md:flex-row items-center justify-center md:gap-20 mt-4 md:mt-0">
        <div class="flex items-center justify-center">
          <div class="text-center md:text-left">
          <h1 class="text-lg md:text-3xl font-bold text-secondary ">What are</h1>
          <h1 class="text-xl md:text-4xl font-bold text-secondary">RETAINERS ?</h1>
          <p class="pt-4 pb-6 max-w-[600px]">These are upfront payment fees to secure services over long term. Fees are deducted monthly from the retainer so clients do not need to make monthly payments.</p>
          <span class="btn bg-secondary" @click="scrollToSection('contact')">Message Us</span>
          </div>
        </div>
        <div class="flex flex-col items-center justify-center mt-10">
          <h1 class="text-xl md:text-3xl font-bold text-secondary mb-2">BENEFITS</h1>
          <Carousel/>
        </div>
      </div>
    </div>
  </div>
</template>


<style lang="scss" scoped></style>
