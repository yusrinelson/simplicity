<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import logo from "../assets/images/logo.png";

const activeSection = ref("home");

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

// Track active section while scrolling
const handleScroll = () => {
  const sections = ["home", "about", "services", "packages", "contact"];
  const scrollPosition = window.scrollY + 150;

  for (const sectionId of sections) {
    const element = document.getElementById(sectionId);
    if (element) {
      const { offsetTop, offsetHeight } = element;
      if (scrollPosition >= offsetTop && scrollPosition < offsetTop + offsetHeight) {
        activeSection.value = sectionId;
        break;
      }
    }
  }
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
  handleScroll(); // Set initial active section
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<template>
  <div class="w-full flex justify-center items-center font-semibold fixed z-50">
    <div
      class="flex items-center justify-between w-[60vw] bg-white bg-opacity-50 backdrop-blur-md mt-4 p-4 rounded-[50px] shadow-md"
    >
      <div class="ml-4 cursor-pointer" @click="scrollToSection('home')">
        <img :src="logo" alt="logo" height="60" width="60" />
      </div>

      <!-- Navigation Links -->
      <ul class="flex items-center gap-8">
        <li
          @click="scrollToSection('home')"
          :class="[
            'hover:text-primary cursor-pointer transition-colors',
            activeSection === 'home' ? 'text-primary font-bold' : '',
          ]"
        >
          Home
        </li>
        <li
          @click="scrollToSection('about')"
          :class="[
            'hover:text-primary cursor-pointer transition-colors',
            activeSection === 'about' ? 'text-primary font-bold' : '',
          ]"
        >
          About
        </li>
        <li
          @click="scrollToSection('services')"
          :class="[
            'hover:text-primary cursor-pointer transition-colors',
            activeSection === 'services' ? 'text-primary font-bold' : '',
          ]"
        >
          Services
        </li>
        <li
          @click="scrollToSection('packages')"
          :class="[
            'hover:text-primary cursor-pointer transition-colors',
            activeSection === 'packages' ? 'text-primary font-bold' : '',
          ]"
        >
          Packages
        </li>
      </ul>

      <span
        @click="scrollToSection('contact')"
        class="btn bg-primary hover:bg-secondary cursor-pointer transition-colors"
      >
        Contact
      </span>
    </div>
  </div>
</template>

<style>
</style>
