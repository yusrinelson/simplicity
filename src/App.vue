<script setup>
// import { RouterLink, RouterView } from 'vue-router'
import HomeView from './views/HomeView.vue'
import { useHead } from '@vueuse/head'

useHead({
  title: 'Simplicity HR Solutions - Professional HR Services',
  meta: [
    {
      name: 'description',
      content: 'Simplicity HR Solutions provides expert HR consulting, recruitment, and workforce management services across South Africa. Transform your business with our professional HR solutions.'
    },
    {
      name: 'keywords',
      content: 'HR solutions, human resources, HR consulting, recruitment services, South Africa HR, workforce management, employee relations, Simplicity HR'
    },
    {
      property: 'og:title',
      content: 'Simplicity HR Solutions - Professional HR Services'
    }
  ]
})
</script>

<template>

      <HomeView/>
      <!-- <nav> -->
        <!-- <RouterLink to="/">Home</RouterLink> -->
      <!-- </nav> -->
  <!-- <RouterView /> -->
</template>

<style scoped>
/* header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
} */
</style>
