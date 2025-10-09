<script setup>
import { ref } from 'vue'

const testimonials = [
  {
    id: 1,
    description: `We would like to express our sincere appreciation for Ms. Robin Philander, whose dedication and professionalism have been an incredible asset to Beach House Academy. Her exceptional service, commitment, and work ethic have greatly contributed to the growth and stability of our institution over the past year and a half.
    <br/>
    <br/>
    Without her support, Beach House Academy would not be where it is today. We commend Ms. Philander for her excellent performance and unwavering dedication.
    <br/>
    <br/>
    We at Beach House Academy deeply appreciate her continued efforts and are pleased to confirm that we will be continuing our partnership with Simplicity Outsourcing on a permanent basis.

    `,
    title: "Amber Basson",
    company: "Beach House Academy Management",
  },
  {
    id: 2,
    description: `Robin has been an absolute pleasure to work with,Her commitment to getting the job done is outstanding. 
    <br/>
    <br/>
    SimplicityHr is an amazing company.Thank you for all your help and eagerness.`,
    title: "Zoe",
    company: "Strategic logistics",
  },
];

const expandedStates = ref({});

const toggleExpanded = (id) => {
  expandedStates.value[id] = !expandedStates.value[id];
};

const truncateText = (text, maxLength = 347) => {
  if (text.length <= maxLength) return text;
  return text.substring(0, maxLength);
};

const getDisplayText = (testimonial) => {
  const isExpanded = expandedStates.value[testimonial.id];
  if (isExpanded || testimonial.description.length <= 337) {
    return testimonial.description;
  }
  return truncateText(testimonial.description, 337) + '...';
};

const shouldShowButton = (description) => {
  return description.length > 337;
};
</script>

<template>
  <div class="body bg-background mb-8">
    <div class="flex items-center flex-col">
      <h1 class="heading">TESTIMONIALS</h1>
      <p class="subheading text-secondary">
        What our clients have to say about us
      </p>
    </div>
    
    <div class="flex flex-col md:flex-row gap-8 max-w-6xl mx-auto mt-6 md:mt-10">
      <div 
        v-for="testimonial in testimonials" 
        :key="testimonial.id" 
        class="bg-white rounded-2xl p-4 md:p-8 flex-1 relative shadow-lg border-l-4 md:border-l-8 border-b-4 md:border-b-8  border-secondary flex flex-col"
      >
        <!-- Quote Icon -->
        <div class="absolute -top-4 left-4 md:-top-6 md:left-6 w-10 h-10 md:w-16 md:h-16 bg-secondary rounded-full flex items-center justify-center">
          <svg class="w-8 h-8 md:w-12 md:h-12 text-white" viewBox="0 0 24 24" fill="currentColor">
            <path d="M14,17H17L19,13V7H13V13H16M6,17H9L11,13V7H5V13H8L6,17Z" />
          </svg>
        </div>
        
        <!-- Description -->
        <div class="flex-grow">
          <p class="text-gray-700 text-sm md:text-[1rem] leading-[1.3rem] my-4 md:my-6 text-left" v-html="getDisplayText(testimonial)">
          </p>
          
          <!-- See More Button -->
          <button 
            v-if="shouldShowButton(testimonial.description)"
            @click="toggleExpanded(testimonial.id)"
            class="text-secondary hover:text-secondary/80 text-sm font-medium transition-colors duration-200 mb-4"
          >
            {{ expandedStates[testimonial.id] ? 'See Less' : 'See More' }}
          </button>
        </div>
        
        <!-- Author Info -->
        <div class="mt-auto">
          <h4 class="text-[1rem] md:text-lg font-bold text-gray-800 italic md:mb-1">{{ testimonial.title }}</h4>
          <p class="text-xs md:text-sm text-gray-600 italic">{{ testimonial.company }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>