<script setup lang="ts">
const benefits = ref(['100 GB of storage', 'Option to add members', 'Extra Member benefits'])
const cards = ref([
  { title: 'Basic', package: '100 GB', price: '1.99', highlight: false },
  { title: 'Premium', package: '1 TB', price: '12.99', highlight: true },
  { title: 'Enterprice', package: 'Custom', price: '999.99', highlight: false }])
</script>

<template>
  <div>
    <!-- Global container -->
    <div class="flex items-center justify-center min-h-screen bg-slate-800">
      <!-- Inner container -->
      <div
        class="flex flex-col my-6 space-y-6 md:space-y-0 md:space-x-6
      md:flex-row md:my-0"
      >
        <!-- Col 1 -->
        <div v-for="(card, index) in cards" :key="index" :class="{ 'bg-slate-700': !card.highlight, 'bg-violet-600': card.highlight }" class="rounded-xl text-white">
          <!-- Upper container -->
          <div class="p-8 mx-3 mt-3 rounded-t-xl bg-slate-800">
            <div class="text-center uppercase">
              {{ card.title }}
            </div>
            <h2 class="mt-10 font-serif text-5xl text-center">
              {{ card.package }}
            </h2>
            <h3 class="mt-2 text-center">
              ${{ card.price }}/Month
            </h3>
            <div class="flex justify-center">
              <a
                href="#" :class="{ 'bg-violet-600': card.highlight }" class="inline-block px-10 py-3 my-6
               text-center border border-violet-600 rounded-lg
                hover:bg-violet-800 hover:border-violet-800 duration-200"
              >
                Purchase
              </a>
            </div>
          </div>
          <!-- Border -->
          <div class="border-t border-slate-700" />
          <!-- Lower Container -->
          <div class="p-8 mx-3 mb-3 rounded-b-xl bg-slate-800">
            <!-- List Container -->
            <div v-for="(item, index) in benefits" :key="index" class="flex flex-col space-y-2">
              <!-- List Item 1 -->
              <div class="flex justify-center">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="w-5 h-5"
                  viewBox="0 0 24 24"
                  stroke-width="2"
                  stroke="currentColor"
                  fill="none"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                  <path d="M5 12l5 5l10 -10" />
                </svg>
                <span class="text-sm ml-1">{{ item }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
