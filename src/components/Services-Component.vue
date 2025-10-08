<script setup>
import { DocumentTextIcon, UserGroupIcon,
  ClipboardDocumentListIcon,
  GlobeAltIcon, CalculatorIcon} from '@heroicons/vue/24/outline'
const services = [
  {
    icon: DocumentTextIcon,
    title: "Word Processing",
    description:
      "Professional document creation, formatting, and editing services to keep your business communications polished and professional.",
    list: [
      "Word processing and spreadsheet design",
      "Proof reading and editing",
      "General administrative assistance",
    ],
  },
  {
    icon: UserGroupIcon,
    title: "HR Support",
    description:
      "Comprehensive HR solutions including recruitment assistance, employee relations, and compliance support tailored to your needs.",
    list: [
      "HR support (contracts, recruitment, selection)",
      "Payroll and leave management",
      "Staff appraisals and performance evaluations",
    ],
  },
  {
    icon: ClipboardDocumentListIcon,
    title: "Administrative & Financial Services",
    description:
      "Efficient organization of your administrative tasks, financial processing, and operational management to keep your business running smoothly.",
    list: [
      "Invoicing and billing",
      "Bank allocations",
      "General administrative assistance",
    ],
  },
  {
    icon: GlobeAltIcon,
    title: "Travel & Booking Coordination",
    description:
      "Professional booking and scheduling management to handle all your business travel and accommodation needs seamlessly.",
    list: [
      "Booking flights and accommodation",
      "Travel itinerary management",
      "Administrative scheduling support",
    ],
  },
  {
    icon: CalculatorIcon,
    title: "Tax & Financial Compliance",
    description:
      "Complete tax and financial compliance services to ensure your business meets all regulatory requirements and maintains accurate financial records.",
    list: [
      "SARS eFiling profile setup",
      "Company and personal income tax returns",
      "Annual financial statements preparation",
      "Provisional tax submissions",
    ],
  },
];
</script>

<template>
  <div class="body" id="services">
    <div class="flex items-center flex-col">
      <h1 class="heading">OUR SERVICES</h1>
      <p class="subheading text-secondary">
        Comprehensive solutions for all your administrative and HR needs
      </p>
    </div>
    <div class="w-fit mx-auto">
      <div class="flex flex-wrap items-center justify-center gap-4 mb-4 mt-10">
        <div
          class="service-card bg-gray-100 p-6 w-[240px] h-[330px] rounded-md shadow-md relative overflow-hidden transition-all duration-300 hover:shadow-xl cursor-pointer group"
          v-for="item in services"
          :key="item.title"
        >
          <!-- Default View -->
          <div class="default-content transition-opacity duration-300 group-hover:opacity-0">
            <div class="icon-wrapper mb-4 flex items-center flex-col">
              <span class="text-4xl"><Component :is="item.icon" class="w-8 h-8 text-green-500" /></span>
            <h1 class="text-xl font-bold text-secondary text-center">{{ item.title }}</h1>
            </div>
            <p class="text-sm text-gray-600 leading-relaxed text-center">
              {{ item.description }}
            </p>
            <p class="text-xs text-center mt-4 text-gray-400 italic">Hover to see details</p>
          </div>

          <!-- Hover View -->
          <div
            class="hover-content absolute inset-0 p-6 bg-secondary text-white opacity-0 transition-opacity duration-300 group-hover:opacity-100 flex flex-col"
          >
            <h2 class="text-xl font-bold mb-2">{{ item.title }}</h2>
            <p class="font-semibold mb-3 text-sm">What's included:</p>
            <ul class="space-y-2">
              <li
                v-for="(listItem, index) in item.list"
                :key="index"
                class="flex items-start text-sm"
              >
                <span class="mr-2 text-yellow-400 flex-shrink-0">✓</span>
                <span>{{ listItem }}</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

.default-content {
  position: relative;
  z-index: 1;
}

.hover-content {
  z-index: 2;
}
</style>