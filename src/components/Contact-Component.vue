<script setup>
import { ref } from 'vue';

const formData = ref({
  fullName: '',
  email: '',
  cellNumber: '',
  message: ''
});

const handleSubmit = () => {
  console.log('Form submitted:', formData.value);
  //clear the form after submit
  formData.value = {
    fullName: '',
    email: '',
    cellNumber: '',
    message: ''
  };
};
</script>

<template>
  <div class="body" id="contact">
    <div class="flex items-center flex-col">
      <h1 class="heading">CONTACT US</h1>
      <p class="subheading text-secondary">
        Get in Touch and let's Simplify Together
      </p>
    </div>
     <div class="max-w-6xl mx-auto mt-10 px-4">
      <div class="grid md:grid-cols-2  items-start">
        <!-- Map Section -->
        <div class="w-full h-full min-h-[400px] overflow-hidden shadow-lg">
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3301.9468856137278!2d18.347516876312255!3d-34.147700973121204!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x1dcc6b4406a9c941%3A0xb304e4b4fdaf7cb2!2s12%20Pluto%20Rd%2C%20Ocean%20View%2C%20Cape%20Town%2C%207975!5e0!3m2!1sen!2sza!4v1759841623701!5m2!1sen!2sza"
            title="map"
            width="100%"
            height="100%"
            style="border: 0; min-height: 400px"
            allowfullscreen=""
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"
          ></iframe>
        </div>

        <!-- Contact Form Section -->
        <div class="bg-[#f5e6d3] p-8 shadow-lg">
          <div class="mb-6">
            <h2 class="text-3xl font-bold text-secondary mb-2">Ready to Get Started?</h2>
            <p class="text-gray-700 text-sm">
              Contact us today to discuss which package is right for you
            </p>
          </div>

          <form @submit.prevent="handleSubmit" class="space-y-4">
            <!-- Full Name -->
            <div>
              <input
                v-model="formData.fullName"
                type="text"
                placeholder="Full Name"
                required
                class="w-full px-4 py-3 bg-white/50 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-secondary focus:border-transparent placeholder-gray-500 text-gray-800"
              />
            </div>

            <!-- Email -->
            <div>
              <input
                v-model="formData.email"
                type="email"
                placeholder="Email"
                required
                class="w-full px-4 py-3 bg-white/50 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-secondary focus:border-transparent placeholder-gray-500 text-gray-800"
              />
            </div>

            <!-- Cell Number -->
            <div>
              <input
                v-model="formData.cellNumber"
                type="tel"
                placeholder="Cell Number"
                required
                class="w-full px-4 py-3 bg-white/50 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-secondary focus:border-transparent placeholder-gray-500 text-gray-800"
              />
            </div>

            <!-- Message -->
            <div>
              <textarea
                v-model="formData.message"
                placeholder="Message"
                rows="4"
                required
                class="w-full px-4 py-3 bg-white/50 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-secondary focus:border-transparent placeholder-gray-500 text-gray-800 resize-none"
              ></textarea>
            </div>

            <!-- Submit Button -->
            <div>
              <button
                type="submit"
                class="w-full bg-[#1e3a5f] text-white font-bold py-3 px-6 rounded-md hover:bg-[#152d4a] transition-colors duration-300 shadow-md hover:shadow-lg"
              >
                Send Message
              </button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>


<style lang="scss" scoped></style>
