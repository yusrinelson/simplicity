<script setup>
import { Carousel, Slide, Navigation } from 'vue3-carousel'
import 'vue3-carousel/carousel.css'
import {
  CurrencyDollarIcon,
  BoltIcon,
  ChatBubbleLeftRightIcon,
  CalendarDaysIcon
} from '@heroicons/vue/24/outline'

// Example images
const items = [
  {
    title: 'Cost Effective',
    icon: CurrencyDollarIcon,
    description: 'Save money with affordable pricing plans.',
  },
  {
    title: 'Priority',
    icon: BoltIcon,
    description: 'Your requests get top priority.',
  },
  {
    title: 'Better Communication',
    icon: ChatBubbleLeftRightIcon,
    description: 'Stay connected with clear and fast communication.',
  },
  {
    title: 'Predictable',
    icon: CalendarDaysIcon,
    description: 'Reliable services with predictable outcomes.',
  },
]
  
// Carousel configuration
const config = {
  itemsToShow: 1,       // Always 1 image
  gap: 10,
  snapAlign: 'center',
  height: 200,          // Adjust height as needed
  wrapAround: true,
  mouseDrag: true,
  autoplay: 3000,
  pauseAutoplayOnHover: true
  
}
</script>

<template>
  <div class="w-[90vw] md:w-[350px] max-w-4xl mx-auto">
    <Carousel v-bind="config">
      <Slide  v-for="(item, index) in items" :key="index">
        <div class="flex flex-col items-center justify-center w-[350px] h-[200px] bg-primary text-white border border-secondary rounded-lg p-6 text-center shadow-lg">
           <component 
            :is="item.icon" 
            class="w-16 h-16 mb-4 text-green-500"
          />
          <h2 class="text-xl font-bold mb-2">{{ item.title }}</h2>
          <p class="text-sm">{{ item.description }}</p>
        </div>
      </Slide>

      <!-- Navigation arrows -->
      <template #addons>
        <Navigation style="color: white" />
      </template>
    </Carousel>
  </div>
</template>

<style scoped>
/* Optional: override navigation button styles */
.carousel {
  /* --vc-nav-background: white; */
  --vc-nav-border-radius: 50%;
}
</style>
