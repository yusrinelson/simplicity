<script setup>
const fees = [
  {
    name: "Package 1",
    price: "250",
    duration: "/ hour",
    list: [
      "Perfect for once-off tasks",
      "Small administrative projects",
      "No long-term commitment",
      "Pay as you go",
      "Flexible scheduling",
    ],
  },
  {
    name: "Package 2",
    price: "2,250",
    duration: " / month",
    list: [
      "10 hours of dedicated support",
      "Regular HR assistance",
      "Administrative task management",
      "Priority scheduling",
      "Monthly progress reports",
    ],
    note: "Requires a 6-month contract"
  },
  {
    name: "Package 3",
    price: "4,500",
    duration: "/ month",
    list: [
      "20 hours of comprehensive support",
      "Extended business assistance",
      "Full HR & admin coverage",
      "Dedicated account manager",
      "Quarterly business reviews",
    ],
    note: "Requires a 6-month contract"
  },
  {
    name: "Package 4",
    price: "CUSTOM",
    list: [
      "Tailor-made solutions",
      "Customized service packages",
      "Flexible hour allocations",
      "Specialized project support",
      "Scalable as your business grows",
    ],
    note: "Requires a 6-month contract - Contact us for pricing"
  },
];
</script>

<template>
  <div class="body bg-gradient-to-t from-[var(--background)] to-white" id="packages">
    <div class="flex items-center flex-col">
      <h1 class="heading">FEES & PACKAGE PRICES</h1>
      <p class="subheading text-secondary">
        Affordable prices that suit you or your business requirements
      </p>
    </div>
    <div class="flex items-stretch justify-center gap-6 flex-wrap mb-4 mt-6 md:mt-16">
      <div
        class="flex flex-col rounded-md p-4 w-[90vw] sm:w-[250px] min-h-[400px] md:min-h-[435px] shadow-sm shadow-black border-[1px] border-primary hover:bg-primary hover:border-primary hover:shadow-md hover:text-white hover:shadow-black transition-all duration-300 ease-in-out"
        v-for="(fee, index) in fees"
        :key="index"
      >
        <div class="flex flex-col md:items-center md:justify-center">
          <h2 class="text-lg md:text-xl font-bold mb-4">{{ fee.name }}</h2>
          <h1 class="text-2xl">
            <span class="font-bold text-secondary text-4xl md:text-5xl">
              <span v-if="fee.price != 'CUSTOM'" class="text-3xl md:text-4xl">R</span>
              {{ fee.price }}
            </span>
          </h1>
          <p class="text-xl font-semibold text-secondary md:mb-2">{{ fee.duration }}</p>
        </div>

        <!-- Features List (grows to fill space) -->
        <ul class="space-y-2 mb-4 font-semibold flex-grow flex flex-col justify-center">
          <li class="flex items-start" v-for="(item, i) in fee.list" :key="i">
            <span class="text-green-500 mr-2 mt-1">✓</span>
            <span>{{ item }}</span>
          </li>
        </ul>

        <!-- Note (always at bottom) -->
        <p class="italic font-light text-sm text-center mt-auto pt-4">
          {{ fee.note }}
        </p>
      </div>
    </div>
    <p class="text-center">
      <span class="font-bold">NOTE:</span>
      <span class="italic text-sm md:text-base">
        Options 2, 3, and 4 require a 6-month contract to ensure consistent, quality service and
        build a lasting partnership with your business.
      </span>
    </p>
  </div>
</template>

<style lang="scss" scoped></style>