<script setup>
const timelineItems = [
  {
    title: 'THE INSPIRATION',
    description: 'I was inspired to start Simplicity by my love and passion for the career path I choose which is Human Resources Management and my extensive knowledge in the administration world being the back bone of a business itself.'
  },
  {
    title: 'THE WHY',
    description: 'Our aim is to help business alike to thrive and successful so that business owners are focused more on the business itself etc marketing and sales, while the HR and Administration.'
  },
  {
    title: 'THE HOW',
    description: 'Simplicity has 4 packages which consists of hourly and monthly rates to suit each and every business preferences. From taking on the smallest to extensive HR and Administrative business support tasks. Covering the each and every detail of the business administrative side.'
  }
]
</script>

<template>
  <div class="body flex flex-col md:flex-row items-center justify-center  bg-background gap-4 md:gap-20">
    <div class="flex items-center flex-col justify-start">
      <div>
        <h1 class="text-xl md:text-4xl font-semibold text-primary">BEHIND</h1>
        <h1 class="text-xl md:text-4xl font-semibold text-primary">SIMPLICITY</h1>
        <h1 class="text-xl md:text-4xl font-semibold text-primary">EST2022</h1>
        <h1 class="text-lg md:text-3xl font-semibold text-secondary">TIMELINE</h1>
      </div>
    </div>
    <div>
      <div
        v-for="(item, index) in timelineItems"
        :key="index"
        class=" md:w-[450px] h-[fit] border-primary border-2 rounded-md mb-4 relative px-8 py-4"
      >
        <h2 class="text-lg md:text-2xl font-bold text-primary mb-2">{{ item.title }}</h2>
        <p class="text-sm md:text-[1rem]">{{ item.description }}</p>
        <div class="w-[30px] h-[30px] bg-primary absolute top-[40%] left-[-15px]"></div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>