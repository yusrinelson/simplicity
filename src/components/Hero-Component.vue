<script setup>
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
    <div class="hero relative h-[100vh] w-full">

  <div class="bg-[linear-gradient(to_bottom,rgba(255,255,255,0.3)_50%,var(--primary)_120%)] w-full h-full flex justify-center items-center flex-col absolute" id="home">

    <h1 class="text-3xl font-semibold mb-8">HR AND ADMINISTRATIVE BUSINESS SUPPORT</h1>
    <h1 class="text-3xl font-semibold">SIMPLIFY YOUR LIFE With Simplicity</h1>
    <p class="text-xl italic">Take your company to the next level and grow your business with Simplicity</p>
    <div class=" flex gap-8 mt-6">
      <span class="btn bg-primary hover:bg-secondary " @click="scrollToSection('packages')">View Pacakges</span>
      <span class="btn bg-secondary hover:bg-primary" @click="scrollToSection('contact')">Get in Touch</span>
    </div>

  </div>
    </div>
</template>

<style scoped>
.hero{
    background: url('../assets/images/hero.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    background-attachment: fixed;
}
</style>
