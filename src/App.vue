<script setup>
import HomeView from './views/HomeView.vue'
import { useHead } from '@vueuse/head'

useHead({
  title: 'Simplicity HR Solutions | HR, Payroll & Administrative Support in South Africa',
  meta: [
    {
      name: 'description',
      content:
        'Streamline your business with Simplicity HR Solutions. We provide HR consulting, payroll management, recruitment, admin support, and tax compliance services throughout South Africa.'
    },
    {
      name: 'keywords',
      content:
        'HR solutions, administrative support, payroll management, human resources South Africa, recruitment, tax compliance, business support services'
    },
    {
      property: 'og:title',
      content:
        'Simplicity HR Solutions | HR, Payroll & Administrative Support in South Africa'
    },
    {
      property: 'og:description',
      content:
        'HR, recruitment, payroll, administrative, and tax compliance services for South African businesses.'
    }
  ]
})
</script>

<template>
  <HomeView />
</template>

<style scoped></style>