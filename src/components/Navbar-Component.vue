<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import logo from "../assets/images/logo.png";

const activeSection = ref("home");
const isMenuOpen = ref(false);

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
  // Close menu after navigation on mobile
  isMenuOpen.value = false;
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

// Toggle mobile menu
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
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
  <div class="w-full flex justify-center items-center font-semibold fixed z-50 px-1 md:px-4">
    <div
      class="flex items-center justify-between w-full md:w-[70vw] lg:w-[60vw] bg-white bg-opacity-50 backdrop-blur-md mt-2 md:mt-4 p-1 md:p-4 rounded-[50px] shadow-md"
    >
      <div class="ml-4 cursor-pointer" @click="scrollToSection('home')">
        <img :src="logo" alt="logo" height="60" width="60" />
      </div>

      <!-- Desktop Navigation Links -->
      <ul class="hidden md:flex items-center gap-8">
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

      <!-- Desktop Contact Button -->
      <span
        @click="scrollToSection('contact')"
        class="hidden md:inline-block btn bg-primary hover:bg-secondary cursor-pointer transition-colors"
      >
        Contact
      </span>

      <!-- Mobile Menu Button (Hamburger) -->
      <button
        @click="toggleMenu"
        class="md:hidden flex flex-col gap-1.5 p-2 mr-2 focus:outline-none"
        aria-label="Toggle menu"
      >
        <span
          :class="[
            'block w-6 h-0.5 bg-primary transition-all duration-300',
            isMenuOpen ? 'rotate-45 translate-y-2' : '',
          ]"
        ></span>
        <span
          :class="[
            'block w-6 h-0.5 bg-primary transition-all duration-300',
            isMenuOpen ? 'opacity-0' : '',
          ]"
        ></span>
        <span
          :class="[
            'block w-6 h-0.5 bg-primary transition-all duration-300',
            isMenuOpen ? '-rotate-45 -translate-y-2' : '',
          ]"
        ></span>
      </button>
    </div>

    <!-- Mobile Dropdown Menu -->
    <transition
      enter-active-class="transition duration-200 ease-out"
      enter-from-class="opacity-0 translate-y-[-10px]"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition duration-150 ease-in"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 translate-y-[-10px]"
    >
      <div
        v-if="isMenuOpen"
        class="md:hidden fixed top-[4.5rem] right-2 min-w-60 bg-white bg-opacity-50 backdrop-blur-md rounded-2xl shadow-lg p-4"
      >
        <ul class="flex flex-col gap-4">
          <li
            @click="scrollToSection('home')"
            :class="[
              'hover:text-primary cursor-pointer transition-colors py-2 px-4 rounded-lg hover:bg-gray-100',
              activeSection === 'home' ? 'text-primary font-bold bg-gray-50' : '',
            ]"
          >
            Home
          </li>
          <li
            @click="scrollToSection('about')"
            :class="[
              'hover:text-primary cursor-pointer transition-colors py-2 px-4 rounded-lg hover:bg-gray-100',
              activeSection === 'about' ? 'text-primary font-bold bg-gray-50' : '',
            ]"
          >
            About
          </li>
          <li
            @click="scrollToSection('services')"
            :class="[
              'hover:text-primary cursor-pointer transition-colors py-2 px-4 rounded-lg hover:bg-gray-100',
              activeSection === 'services' ? 'text-primary font-bold bg-gray-50' : '',
            ]"
          >
            Services
          </li>
          <li
            @click="scrollToSection('packages')"
            :class="[
              'hover:text-primary cursor-pointer transition-colors py-2 px-4 rounded-lg hover:bg-gray-100',
              activeSection === 'packages' ? 'text-primary font-bold bg-gray-50' : '',
            ]"
          >
            Packages
          </li>
          <li class="mt-2">
            <span
              @click="scrollToSection('contact')"
              class="block text-center btn bg-primary hover:bg-secondary cursor-pointer transition-colors py-2 px-4 rounded-lg"
            >
              Contact
            </span>
          </li>
        </ul>
      </div>
    </transition>
  </div>
</template>

<style>
</style>