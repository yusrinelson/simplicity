<script setup>
import aboutImage from '../assets/images/about.jpg'
</script>
<template>
  <div class="body grid md:grid-cols-2 bg-gradient-to-b from-[var(--background)] to-white" id="about">
    <div class="flex items-start justify-center flex-col">
      <h1 class=" heading ">WHO ARE WE ?</h1>
      <p class="text-sm md:text-[1rem] mt-4 mb-4 md:mb-0">
        business based on family, loyalty, and compassion. We aim to create long-lasting bonds with
        our clients and their businesses, providing support that goes beyond just administrative
        tasks. We understand that every business is unique, which is why we offer personalized
        solutions tailored to your specific needs. Let us handle the complexities so you can focus
        on what matters most is growing your business.
      </p>
    </div>
    <div class="flex items-center justify-center">
      <img :src="aboutImage" alt="about" class="max-h-[300px] md:h-[300px] w-auto rounded-lg"/>
    </div>
  </div>
</template>


<style lang="scss" scoped></style>
