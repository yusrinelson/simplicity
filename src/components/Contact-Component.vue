<script setup>
import { ref } from "vue";
import emailjs from "@emailjs/browser";

const formData = ref({
  fullName: "",
  email: "",
  cellNumber: "",
  package: "",
  message: "",
});

const isSubmitting = ref(false);
const submitStatus = ref(""); //success or error

const handleSubmit = async () => {
  isSubmitting.value = true;
  submitStatus.value = ''; // Clear previous status

  const serviceID = import.meta.env.VITE_EMAILJS_SERVICE_ID;
  const templateID = import.meta.env.VITE_EMAILJS_TEMPLATE_ID;
  const publicKey = import.meta.env.VITE_EMAILJS_PUBLIC_KEY;

  const templateParams = {
    from_name: formData.value.fullName,
    from_email: formData.value.email,
    cell_number: formData.value.cellNumber,
    package: formData.value.package,
    message: formData.value.message,
  };

  try {
    const response = await emailjs.send(serviceID, templateID, templateParams, publicKey);
    console.log("success!", response.status, response.text);
    submitStatus.value = "success";

    //clear the form after submit
    formData.value = {
      fullName: "",
      email: "",
      cellNumber: "",
      package: "",
      message: "",
    };

    setTimeout(() => {
      submitStatus.value = "";
    }, 5000);
  } catch (error) {
    console.log("failed", error);
    submitStatus.value = "error";
  } finally {
    isSubmitting.value = false;
  }
};
</script>

<template>
  <div class="body" id="contact">
    <div class="flex items-center flex-col">
      <h1 class="heading">CONTACT US</h1>
      <p class="subheading text-secondary">Get in Touch and let's Simplify Together</p>
    </div>
    <div class="max-w-6xl mx-auto mt-10 px-4">
      <div class="grid md:grid-cols-2 items-start">
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
                :disabled="isSubmitting"
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
                :disabled="isSubmitting"
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
                :disabled="isSubmitting"
                class="w-full px-4 py-3 bg-white/50 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-secondary focus:border-transparent placeholder-gray-500 text-gray-800"
              />
            </div>

            <!-- selcet options for package 1,2,3 or 4 -->
            <div>
              <select
                v-model="formData.package"
                required
                :disabled="isSubmitting"
                class="w-full px-4 py-3 bg-white/50 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-secondary focus:border-transparent text-gray-500"
                :class="{ 'text-gray-400': !formData.package }"
              >
                <!-- Placeholder option -->
                <option value="" disabled selected hidden>Select Package</option>

                <!-- Options -->
                <option value="package1">Package 1</option>
                <option value="package2">Package 2</option>
                <option value="package3">Package 3</option>
                <option value="package4">Package 4</option>
              </select>
            </div>

            <!-- Message -->
            <div>
              <textarea
                v-model="formData.message"
                placeholder="Message"
                rows="4"
                required
                :disabled="isSubmitting"
                class="w-full px-4 py-3 bg-white/50 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-secondary focus:border-transparent placeholder-gray-500 text-gray-800 resize-none"
              ></textarea>
            </div>

            <!-- Submit Button -->
            <div>
              <button
                type="submit"
                :disabled="isSubmitting"
                class="w-full bg-[#1e3a5f] text-white font-bold py-3 px-6 rounded-md hover:bg-[#152d4a] transition-colors duration-300 shadow-md hover:shadow-lg disabled:opacity-50 disabled:cursor-not-allowed disabled:hover:bg-[#1e3a5f]"
              >
                <span v-if="isSubmitting" class="flex items-center justify-center">
                  <svg class="animate-spin -ml-1 mr-3 h-5 w-5 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                    <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                    <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                  </svg>
                  Sending...
                </span>
                <span v-else>Send Message</span>
              </button>
            </div>
            <div
              v-if="submitStatus === 'success'"
              class="mb-4 p-4 bg-green-100 border border-green-400 text-green-700 rounded-md"
            >
              ✓ Message sent successfully! We'll get back to you soon.
            </div>
            <div
              v-if="submitStatus === 'error'"
              class="mb-4 p-4 bg-red-100 border border-red-400 text-red-700 rounded-md"
            >
              ✗ Failed to send message. Please try again.
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
