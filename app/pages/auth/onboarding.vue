<template>
  <section class="py-16 px-4 md:px-8 max-w-7xl mx-auto text-gray-600 bg-taupe-50/90">
    
    <div class="flex flex-col md:flex-row md:items-end justify-between mb-8 gap-4">
      <div>
        <div class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-amber-50 border border-amber-200 text-amber-600 text-xs font-semibold mb-3">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-4 h-4">
            <path fill-rule="evenodd" d="M7.5 6a4.5 4.5 0 1 1 9 0 4.5 4.5 0 0 1-9 0ZM3.751 20.105a8.25 8.25 0 0 1 16.498 0 .75.75 0 0 1-.437.695A18.683 18.683 0 0 1 12 22.5c-2.786 0-5.433-.6-7.812-1.7a.75.75 0 0 1-.437-.695Z" clip-rule="evenodd" />
          </svg>
          Account Profile Setup
        </div>
        <h2 class="text-3xl font-extrabold text-gray-900 tracking-tight">Complete Your Onboarding</h2>
        <p class="text-gray-500 mt-1">Set up your profile details to start creating or participating in Nigerian research surveys.</p>
      </div>

      <a href="#" class="inline-flex items-center gap-1.5 text-indigo-600 font-semibold hover:text-indigo-700 transition-colors text-sm">
        Need assistance? 
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="w-4 h-4">
          <path fill-rule="evenodd" d="M3 10a.75.75 0 0 1 .75-.75h10.638L10.23 5.29a.75.75 0 1 1 1.04-1.08l5.5 5.25a.75.75 0 0 1 0 1.08l-5.5 5.25a.75.75 0 1 1-1.04-1.08l4.158-3.96H3.75A.75.75 0 0 1 3 10Z" clip-rule="evenodd" />
        </svg>
      </a>
    </div>

    <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-start">
      
      <div class="lg:col-span-7 bg-white rounded-2xl border border-gray-100 shadow-md p-6 sm:p-8 space-y-8">
        
        <div class="border-b border-gray-100 pb-4 flex items-center justify-between">
          <span class="text-xs font-bold uppercase tracking-wider text-indigo-600">Profile Information</span>
          <span class="text-xs text-gray-400">Step 1 of 1</span>
        </div>

        <form @submit.prevent class="space-y-6">
          
          <div>
            <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Select Account Type</label>
            <div class="grid grid-cols-2 gap-3 p-1 bg-gray-50 border border-gray-200 rounded-xl">
              <button 
                type="button" 
                @click="profile.accountType = 'Personal'"
                :class="profile.accountType === 'Personal' ? 'bg-indigo-600 text-white shadow-sm font-bold' : 'text-gray-600 hover:text-gray-900 font-medium'"
                class="py-3 px-4 rounded-lg text-sm text-center transition-all duration-200"
              >
                Personal Account
              </button>
              <button 
                type="button" 
                @click="profile.accountType = 'Business'"
                :class="profile.accountType === 'Business' ? 'bg-indigo-600 text-white shadow-sm font-bold' : 'text-gray-600 hover:text-gray-900 font-medium'"
                class="py-3 px-4 rounded-lg text-sm text-center transition-all duration-200"
              >
                Business / Enterprise
              </button>
            </div>
          </div>

          <div v-if="profile.accountType === 'Personal'" class="space-y-6 pt-2">
            
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Username</label>
                <input 
                  v-model="profile.personal.username" 
                  type="text" 
                  placeholder="e.g. ibrahim_agri" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>

              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Age</label>
                <input 
                  v-model.number="profile.personal.age" 
                  type="number" 
                  min="18" 
                  max="100" 
                  placeholder="28" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">State of Residence</label>
                <select 
                  v-model="profile.personal.state" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                >
                  <option value="" disabled>Select State</option>
                  <option v-for="state in nigerianStates" :key="state" :value="state">{{ state }}</option>
                </select>
              </div>

              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Marital Status</label>
                <select 
                  v-model="profile.personal.maritalStatus" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                >
                  <option value="Single">Single</option>
                  <option value="Married">Married</option>
                  <option value="Divorced">Divorced</option>
                  <option value="Widowed">Widowed</option>
                </select>
              </div>
            </div>

            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Location Coverage</label>
              <select 
                v-model="profile.personal.locationScope" 
                class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
              >
                <option value="Nationwide">Nationwide (All States)</option>
                <option value="State Specific">State Specific</option>
              </select>
            </div>

            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Monthly Income (LSM/SEC Band)</label>
              <select 
                v-model="profile.personal.incomeBracket" 
                class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
              >
                <option value="Under ₦50k">Under ₦50,000</option>
                <option value="₦50k-₦150k">₦50,000 - ₦150,000</option>
                <option value="₦150k-₦300k">₦150,000 - ₦300,000</option>
                <option value="₦300k-₦500k">₦300,000 - ₦500,000</option>
                <option value="Above ₦500k">Above ₦500,000</option>
              </select>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Education Level Attained</label>
                <select 
                  v-model="profile.personal.educationLevel" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                >
                  <option value="O'Level (WAEC/NECO)">O'Level (WAEC/NECO)</option>
                  <option value="OND/HND">OND / HND</option>
                  <option value="Bachelor's Degree">Bachelor's Degree</option>
                  <option value="Postgraduate/Master's">Postgraduate Degree</option>
                </select>
              </div>

              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Employment Status</label>
                <select 
                  v-model="profile.personal.employmentStatus" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                >
                  <option value="Formal Corporate">Formal Corporate</option>
                  <option value="Informal/Trader">Informal / Trader</option>
                  <option value="Student">Student</option>
                  <option value="NYSC Corp Member">NYSC Corp Member</option>
                  <option value="Unemployed">Unemployed</option>
                </select>
              </div>
            </div>

          </div>

          <div v-else class="space-y-6 pt-2">
            
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Business Name</label>
                <input 
                  v-model="profile.business.businessName" 
                  type="text" 
                  placeholder="e.g. Olam Agri Nigeria" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>

              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Year of Incorporation</label>
                <input 
                  v-model.number="profile.business.yearIncorporated" 
                  type="number" 
                  min="1900" 
                  max="2026" 
                  placeholder="2012" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>
            </div>

            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Official Website</label>
              <input 
                v-model="profile.business.website" 
                type="url" 
                placeholder="https://www.company.ng" 
                class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
              />
            </div>

            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Business Description</label>
              <textarea 
                v-model="profile.business.description" 
                rows="3" 
                placeholder="Describe your agribusiness or enterprise operations..." 
                class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition resize-none"
              ></textarea>
            </div>

            <div class="space-y-3 pt-2 border-t border-gray-100">
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500">Social Media Profiles</label>
              
              <div class="relative">
                <span class="absolute inset-y-0 left-0 pl-3.5 flex items-center text-gray-400 text-xs font-semibold">FB</span>
                <input 
                  v-model="profile.business.facebook" 
                  type="text" 
                  placeholder="facebook.com/yourbusiness" 
                  class="w-full pl-10 pr-4 py-2.5 rounded-xl border border-gray-200 text-gray-900 text-xs focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>

              <div class="relative">
                <span class="absolute inset-y-0 left-0 pl-3.5 flex items-center text-gray-400 text-xs font-semibold">IG</span>
                <input 
                  v-model="profile.business.instagram" 
                  type="text" 
                  placeholder="@yourbusiness" 
                  class="w-full pl-10 pr-4 py-2.5 rounded-xl border border-gray-200 text-gray-900 text-xs focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>

              <div class="relative">
                <span class="absolute inset-y-0 left-0 pl-3.5 flex items-center text-gray-400 text-xs font-semibold">YT</span>
                <input 
                  v-model="profile.business.youtube" 
                  type="text" 
                  placeholder="youtube.com/c/yourbusiness" 
                  class="w-full pl-10 pr-4 py-2.5 rounded-xl border border-gray-200 text-gray-900 text-xs focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>
            </div>

          </div>

          <div class="pt-4 border-t border-gray-100">
            <button 
              type="submit" 
              class="w-full py-4 px-6 bg-indigo-600 hover:bg-indigo-700 text-white text-base font-bold rounded-xl flex items-center justify-center gap-2 shadow-lg hover:shadow-indigo-200 transition-all duration-200 cursor-pointer"
            >
              <span>Save & Complete Profile</span>
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="w-5 h-5">
                <path fill-rule="evenodd" d="M3 10a.75.75 0 0 1 .75-.75h10.638L10.23 5.29a.75.75 0 1 1 1.04-1.08l5.5 5.25a.75.75 0 0 1 0 1.08l-5.5 5.25a.75.75 0 1 1-1.04-1.08l4.158-3.96H3.75A.75.75 0 0 1 3 10Z" clip-rule="evenodd" />
              </svg>
            </button>
            <p class="text-center text-xs text-gray-400 mt-2">
              Your information is encrypted and securely linked to your account.
            </p>
          </div>

        </form>
      </div>

      <div class="lg:col-span-5 lg:sticky lg:top-8 space-y-4">
        <div class="flex items-center justify-between px-1">
          <span class="text-xs font-bold uppercase tracking-wider text-gray-400">Live Profile Card Preview</span>
          <span class="inline-flex items-center gap-1 text-[11px] text-emerald-600 font-semibold">
            <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span> {{ profile.accountType }} Profile
          </span>
        </div>

        <div v-if="profile.accountType === 'Personal'" class="w-full bg-white rounded-2xl border border-gray-100 shadow-xl p-6 space-y-5">
          <div class="flex items-center gap-4">
            <div class="w-12 h-12 rounded-2xl bg-indigo-600 text-white font-black text-sm flex items-center justify-center uppercase">
              {{ personalAvatarInitials }}
            </div>
            <div>
              <h3 class="text-base font-bold text-gray-900">@{{ profile.personal.username || 'username' }}</h3>
              <p class="text-xs text-gray-500">{{ profile.personal.employmentStatus }} • {{ profile.personal.age || '--' }} yrs</p>
            </div>
          </div>

          <div class="grid grid-cols-2 gap-3 py-3 px-4 bg-gray-50 rounded-xl text-xs">
            <div>
              <span class="text-gray-400 block text-[10px] uppercase font-medium">State</span>
              <span class="font-bold text-gray-800">{{ profile.personal.state || 'Not Set' }}</span>
            </div>
            <div>
              <span class="text-gray-400 block text-[10px] uppercase font-medium">Marital Status</span>
              <span class="font-bold text-gray-800">{{ profile.personal.maritalStatus }}</span>
            </div>
            <div>
              <span class="text-gray-400 block text-[10px] uppercase font-medium">Education</span>
              <span class="font-bold text-gray-800">{{ profile.personal.educationLevel }}</span>
            </div>
            <div>
              <span class="text-gray-400 block text-[10px] uppercase font-medium">Income Bracket</span>
              <span class="font-bold text-gray-800">{{ profile.personal.incomeBracket }}</span>
            </div>
          </div>

          <div class="p-3 bg-indigo-50/60 border border-indigo-100 rounded-xl text-xs text-indigo-700">
            <strong>Targeting Scope:</strong> {{ profile.personal.locationScope }} respondent coverage eligible.
          </div>
        </div>

        <div v-else class="w-full bg-white rounded-2xl border border-gray-100 shadow-xl p-6 space-y-5">
          <div class="flex items-center justify-between">
            <div class="flex items-center gap-3">
              <div class="w-12 h-12 rounded-2xl bg-emerald-700 text-white font-black text-sm flex items-center justify-center uppercase">
                {{ businessAvatarInitials }}
              </div>
              <div>
                <h3 class="text-base font-bold text-gray-900">{{ profile.business.businessName || 'Business Name' }}</h3>
                <div class="flex items-center gap-1 text-[11px] text-emerald-600 font-medium">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="w-3.5 h-3.5">
                    <path fill-rule="evenodd" d="M10 18a8 8 0 1 0 0-16 8 8 0 0 0 0 16Zm3.857-9.809a.75.75 0 0 0-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 1 0-1.06 1.061l2.5 2.5a.75.75 0 0 0 1.137-.089l4-5.5Z" clip-rule="evenodd" />
                  </svg>
                  Verified Enterprise
                </div>
              </div>
            </div>
            <span class="text-xs font-medium text-gray-400">Est. {{ profile.business.yearIncorporated || '----' }}</span>
          </div>

          <p class="text-xs text-gray-500 line-clamp-3">
            {{ profile.business.description || 'Provide a short description of your agribusiness or corporate research goals...' }}
          </p>

          <div class="pt-2 border-t border-gray-100 flex flex-wrap gap-2 text-[11px] text-indigo-600">
            <span v-if="profile.business.website" class="bg-indigo-50 px-2 py-1 rounded-md">{{ profile.business.website }}</span>
            <span v-if="profile.business.facebook" class="bg-gray-100 text-gray-600 px-2 py-1 rounded-md">FB Connected</span>
            <span v-if="profile.business.instagram" class="bg-gray-100 text-gray-600 px-2 py-1 rounded-md">IG Connected</span>
            <span v-if="profile.business.youtube" class="bg-gray-100 text-gray-600 px-2 py-1 rounded-md">YT Connected</span>
          </div>
        </div>

        <div class="p-4 bg-amber-50/60 border border-amber-200/60 rounded-xl space-y-2">
          <div class="flex justify-between items-center text-xs text-amber-800 font-bold">
            <span>Profile Completeness</span>
            <span>100%</span>
          </div>
          <div class="w-full bg-amber-200 rounded-full h-1.5">
            <div class="bg-amber-600 h-1.5 rounded-full w-full"></div>
          </div>
        </div>

      </div>

    </div>
  </section>
</template>

<script setup>
import { reactive, computed } from 'vue'

const nigerianStates = [
  'Abia', 'Adamawa', 'Akwa Ibom', 'Anambra', 'Bauchi', 'Bayelsa', 'Benue', 'Borno',
  'Cross River', 'Delta', 'Ebonyi', 'Edo', 'Ekiti', 'Enugu', 'FCT Abuja', 'Gombe',
  'Imo', 'Jigawa', 'Kaduna', 'Kano', 'Katsina', 'Kebbi', 'Kogi', 'Kwara', 'Lagos',
  'Nasarawa', 'Niger', 'Ogun', 'Ondo', 'Osun', 'Oyo', 'Plateau', 'Rivers', 'Sokoto',
  'Taraba', 'Yobe', 'Zamfara'
]

// Profile Reactive Model linked 1-to-1 to the user
const profile = reactive({
  accountType: 'Personal', // 'Personal' or 'Business'
  
  // Personal Profile Fields
  personal: {
    username: '',
    age: null,
    state: 'Lagos',
    maritalStatus: 'Single',
    locationScope: 'Nationwide',
    incomeBracket: '₦50k-₦150k',
    educationLevel: "Bachelor's Degree",
    employmentStatus: 'Formal Corporate'
  },

  // Business Profile Fields
  business: {
    businessName: '',
    website: '',
    description: '',
    yearIncorporated: 2020,
    facebook: '',
    instagram: '',
    youtube: ''
  }
})

// Avatar Initials Helpers
const personalAvatarInitials = computed(() => {
  if (profile.personal.username) {
    return profile.personal.username.substring(0, 2).toUpperCase()
  }
  return 'USR'
})

const businessAvatarInitials = computed(() => {
  if (profile.business.businessName) {
    const words = profile.business.businessName.trim().split(' ')
    if (words.length >= 2) return (words[0][0] + words[1][0]).toUpperCase()
    return profile.business.businessName.substring(0, 3).toUpperCase()
  }
  return 'BIZ'
})
</script>