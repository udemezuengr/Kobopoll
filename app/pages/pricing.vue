<template>
  <section class="py-16 px-4 md:px-8 max-w-7xl mx-auto text-gray-600 bg-taupe-50/90">
    
    <div class="flex flex-col md:flex-row md:items-end justify-between mb-12 gap-4">
      <div>
        <div class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-amber-50 border border-amber-200 text-amber-600 text-xs font-semibold mb-3">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-4 h-4">
            <path d="M12 7.5a4.5 4.5 0 1 1 0 9 4.5 4.5 0 0 1 0-9Z" />
            <path fill-rule="evenodd" d="M12 1.75a10.25 10.25 0 1 0 0 20.5 10.25 10.25 0 0 0 0-20.5ZM3.25 12a8.75 8.75 0 1 1 17.5 0 8.75 8.75 0 0 1-17.5 0Z" clip-rule="evenodd" />
          </svg>
          Transparent Platform Pricing
        </div>
        <h2 class="text-3xl font-extrabold text-gray-900 tracking-tight">Simple Plans for Research & Data</h2>
        <p class="text-gray-500 mt-1">Scale your field data collection across Nigeria with zero hidden fees.</p>
      </div>

      <div class="inline-flex items-center bg-white p-1 rounded-xl border border-gray-200 shadow-sm">
        <button 
          type="button" 
          @click="billingCycle = 'payg'" 
          :class="billingCycle === 'payg' ? 'bg-indigo-600 text-white font-semibold' : 'text-gray-500 hover:text-gray-900 font-medium'"
          class="px-4 py-2 text-xs rounded-lg transition-all duration-200"
        >
          Pay-As-You-Go
        </button>
        <button 
          type="button" 
          @click="billingCycle = 'monthly'" 
          :class="billingCycle === 'monthly' ? 'bg-indigo-600 text-white font-semibold' : 'text-gray-500 hover:text-gray-900 font-medium'"
          class="px-4 py-2 text-xs rounded-lg transition-all duration-200 flex items-center gap-1.5"
        >
          <span>Monthly Subscription</span>
          <span class="px-1.5 py-0.5 rounded-full bg-emerald-100 text-emerald-700 text-[10px] font-bold">Save 20%</span>
        </button>
      </div>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-8 items-stretch">
      
      <div class="bg-white rounded-2xl border border-gray-100 shadow-md hover:shadow-xl transition-all duration-300 p-6 sm:p-8 flex flex-col justify-between">
        <div>
          <div class="flex items-center justify-between mb-4">
            <span class="px-2.5 py-1 text-xs font-semibold bg-gray-100 text-gray-700 rounded-lg">Pay-As-You-Go</span>
            <span class="text-xs text-gray-400 font-medium">Individual & Students</span>
          </div>

          <h3 class="text-xl font-bold text-gray-900 mb-2">Starter Researcher</h3>
          <p class="text-xs text-gray-500 mb-6">Ideal for quick academic surveys or one-off agribusiness market checks.</p>

          <div class="mb-6 p-4 bg-gray-50 rounded-xl">
            <div class="flex items-baseline gap-1">
              <span class="text-3xl font-black text-gray-900">₦0</span>
              <span class="text-xs text-gray-500 font-medium">/ month platform fee</span>
            </div>
            <p class="text-xs font-semibold text-emerald-600 mt-2">
              + ₦500 minimum per response payout
            </p>
          </div>

          <ul class="space-y-3 text-xs text-gray-600 mb-8">
            <li class="flex items-center gap-2">
              <svg class="w-4 h-4 text-emerald-600 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd"/></svg>
              <span>Basic State & Nationwide Location Filters</span>
            </li>
            <li class="flex items-center gap-2">
              <svg class="w-4 h-4 text-emerald-600 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd"/></svg>
              <span>Single & Multiple Choice Questions</span>
            </li>
            <li class="flex items-center gap-2">
              <svg class="w-4 h-4 text-emerald-600 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd"/></svg>
              <span>Up to 250 Max Correspondents</span>
            </li>
            <li class="flex items-center gap-2">
              <svg class="w-4 h-4 text-emerald-600 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd"/></svg>
              <span>Standard Response Delivery (48 hrs)</span>
            </li>
          </ul>
        </div>

        <NuxtLink 
          to="/signup" 
          class="w-full py-3 px-4 bg-gray-900 hover:bg-gray-800 text-white text-sm font-bold rounded-xl flex items-center justify-center gap-2 transition duration-200"
        >
          Start Free
        </NuxtLink>
      </div>

      <div class="bg-white rounded-2xl border-2 border-indigo-600 shadow-xl p-6 sm:p-8 flex flex-col justify-between relative">
        <div class="absolute -top-3.5 left-1/2 -translate-x-1/2 px-3 py-1 bg-indigo-600 text-white text-[10px] font-extrabold uppercase tracking-widest rounded-full shadow-md">
          Most Popular Enterprise Choice
        </div>

        <div>
          <div class="flex items-center justify-between mb-4">
            <span class="px-2.5 py-1 text-xs font-semibold bg-indigo-50 text-indigo-700 rounded-lg">Agribusiness Pro</span>
            <span class="text-xs text-indigo-600 font-bold">Recommended</span>
          </div>

          <h3 class="text-xl font-bold text-gray-900 mb-2">Growth Enterprise</h3>
          <p class="text-xs text-gray-500 mb-6">Designed for growing agribusinesses needing continuous market feedback.</p>

          <div class="mb-6 p-4 bg-indigo-50/50 border border-indigo-100 rounded-xl">
            <div class="flex items-baseline gap-1">
              <span class="text-3xl font-black text-gray-900">
                {{ billingCycle === 'monthly' ? '₦45,000' : '₦36,000' }}
              </span>
              <span class="text-xs text-gray-500 font-medium">/ month</span>
            </div>
            <p class="text-xs font-semibold text-emerald-600 mt-2">
              + Reduced ₦350 per response payout rate
            </p>
          </div>

          <ul class="space-y-3 text-xs text-gray-600 mb-8">
            <li class="flex items-center gap-2">
              <svg class="w-4 h-4 text-emerald-600 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd"/></svg>
              <span><strong>Full Demographics:</strong> Income LSM, Education & Age</span>
            </li>
            <li class="flex items-center gap-2">
              <svg class="w-4 h-4 text-emerald-600 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd"/></svg>
              <span>Up to 2,500 Correspondents per Survey</span>
            </li>
            <li class="flex items-center gap-2">
              <svg class="w-4 h-4 text-emerald-600 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd"/></svg>
              <span>Priority Live Feed Queueing (24 hr turnaround)</span>
            </li>
            <li class="flex items-center gap-2">
              <svg class="w-4 h-4 text-emerald-600 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd"/></svg>
              <span>CSV & Excel Raw Data Export</span>
            </li>
          </ul>
        </div>

        <NuxtLink 
          to="/signup" 
          class="w-full py-3.5 px-4 bg-indigo-600 hover:bg-indigo-700 text-white text-sm font-bold rounded-xl flex items-center justify-center gap-2 shadow-lg hover:shadow-indigo-200 transition duration-200"
        >
          Subscribe & Launch
        </NuxtLink>
      </div>

      <div class="bg-white rounded-2xl border border-gray-100 shadow-md hover:shadow-xl transition-all duration-300 p-6 sm:p-8 flex flex-col justify-between">
        <div>
          <div class="flex items-center justify-between mb-4">
            <span class="px-2.5 py-1 text-xs font-semibold bg-amber-50 text-amber-700 rounded-lg">Custom Volume</span>
            <span class="text-xs text-gray-400 font-medium">Large Agribusinesses</span>
          </div>

          <h3 class="text-xl font-bold text-gray-900 mb-2">Corporate Enterprise</h3>
          <p class="text-xs text-gray-500 mb-6">For major processors, FMCG supply chains, and government policy studies.</p>

          <div class="mb-6 p-4 bg-gray-50 rounded-xl">
            <div class="flex items-baseline gap-1">
              <span class="text-2xl font-black text-gray-900">Custom Pricing</span>
            </div>
            <p class="text-xs font-semibold text-emerald-600 mt-2">
              Volume discounts on 10k+ respondents
            </p>
          </div>

          <ul class="space-y-3 text-xs text-gray-600 mb-8">
            <li class="flex items-center gap-2">
              <svg class="w-4 h-4 text-emerald-600 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 0 0-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd"/></svg>
              <span>Unlimited Correspondents & Unlimited Questions</span>
            </li>
            <li class="flex items-center gap-2">
              <svg class="w-4 h-4 text-emerald-600 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 0 0-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 0 01.137-.089l4-5.5z" clip-rule="evenodd"/></svg>
              <span>Dedicated On-Ground Verification Agents</span>
            </li>
            <li class="flex items-center gap-2">
              <svg class="w-4 h-4 text-emerald-600 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 0 0-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd"/></svg>
              <span>Dedicated Account Executive & Custom Analytics</span>
            </li>
            <li class="flex items-center gap-2">
              <svg class="w-4 h-4 text-emerald-600 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 0 0-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd"/></svg>
              <span>Invoice Billing & In-app Team Workspaces</span>
            </li>
          </ul>
        </div>

        <a 
          href="mailto:enterprise@agrisurvey.ng" 
          class="w-full py-3 px-4 bg-gray-100 hover:bg-gray-200 text-gray-800 text-sm font-bold rounded-xl flex items-center justify-center gap-2 transition duration-200"
        >
          Contact Corporate Sales
        </a>
      </div>

    </div>

    <div class="mt-12 p-6 bg-white border border-gray-100 rounded-2xl shadow-sm flex flex-col sm:flex-row items-center justify-between gap-4">
      <div class="flex items-center gap-3">
        <div class="w-10 h-10 rounded-xl bg-amber-50 text-amber-600 flex items-center justify-center font-bold text-lg flex-shrink-0">
          💡
        </div>
        <div>
          <h4 class="text-xs font-bold text-gray-900 uppercase tracking-wider">How do payout funds work?</h4>
          <p class="text-xs text-gray-500">Your total survey cost goes directly toward funding participant airtime, mobile money rewards, and data verification fees.</p>
        </div>
      </div>
      <NuxtLink to="/signup" class="text-xs font-bold text-indigo-600 hover:text-indigo-700 whitespace-nowrap">
        Learn more about payouts →
      </NuxtLink>
    </div>

  </section>
</template>

<script setup>
import { ref } from 'vue'

// Billing toggle reactive state ('payg' or 'monthly')
const billingCycle = ref('monthly')
</script>