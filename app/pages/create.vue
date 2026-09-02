<template>
  <section class="py-16 px-4 md:px-8 max-w-7xl mx-auto text-gray-600 bg-taupe-50/90">
    
    <div class="flex flex-col md:flex-row md:items-end justify-between mb-8 gap-4">
      <div>
        <div class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-amber-50 border border-amber-200 text-amber-600 text-xs font-semibold mb-3">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-4 h-4">
            <path fill-rule="evenodd" d="M12 2.25c-5.385 0-9.75 4.365-9.75 9.75s4.365 9.75 9.75 9.75 9.75-4.365 9.75-9.75S17.385 2.25 12 2.25ZM12.75 6a.75.75 0 0 0-1.5 0v5.25H6a.75.75 0 0 0 0 1.5h5.25V18a.75.75 0 0 0 1.5 0v-5.25H18a.75.75 0 0 0 0-1.5h-5.25V6Z" clip-rule="evenodd" />
          </svg>
          Enterprise Research Portal
        </div>
        <h2 class="text-3xl font-extrabold text-gray-900 tracking-tight">Launch a New Agribusiness Survey</h2>
        <p class="text-gray-500 mt-1">Deploy targeted research campaigns to thousands of verified Nigerian participants.</p>
      </div>

      <a href="#" class="inline-flex items-center gap-1.5 text-indigo-600 font-semibold hover:text-indigo-700 transition-colors">
        Back to feed 
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="w-5 h-5">
          <path fill-rule="evenodd" d="M3 10a.75.75 0 0 1 .75-.75h10.638L10.23 5.29a.75.75 0 1 1 1.04-1.08l5.5 5.25a.75.75 0 0 1 0 1.08l-5.5 5.25a.75.75 0 1 1-1.04-1.08l4.158-3.96H3.75A.75.75 0 0 1 3 10Z" clip-rule="evenodd" />
        </svg>
      </a>
    </div>

    <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-start">
      
      <div class="lg:col-span-7 bg-white rounded-2xl border border-gray-100 shadow-md p-6 sm:p-8 space-y-8">
        
        <div class="border-b border-gray-100 pb-4 flex items-center justify-between">
          <span class="text-xs font-bold uppercase tracking-wider text-indigo-600">Survey Builder Configuration</span>
          <span class="text-xs text-gray-400">Live Preview Active</span>
        </div>

        <form @submit.prevent class="space-y-8">
          
          <div class="space-y-4">
            <h3 class="text-sm font-bold text-gray-900 uppercase tracking-wide border-l-4 border-indigo-600 pl-2">
              1. Creator Details
            </h3>

            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Account Type</label>
              <div class="grid grid-cols-2 gap-3">
                <button 
                  type="button" 
                  @click="form.user.accountType = 'Individual'"
                  :class="form.user.accountType === 'Individual' ? 'border-indigo-600 bg-indigo-50 text-indigo-700 font-bold' : 'border-gray-200 text-gray-600 hover:bg-gray-50'"
                  class="py-2.5 px-4 rounded-xl border text-xs text-center transition"
                >
                  Individual Researcher
                </button>
                <button 
                  type="button" 
                  @click="form.user.accountType = 'Business'"
                  :class="form.user.accountType === 'Business' ? 'border-indigo-600 bg-indigo-50 text-indigo-700 font-bold' : 'border-gray-200 text-gray-600 hover:bg-gray-50'"
                  class="py-2.5 px-4 rounded-xl border text-xs text-center transition"
                >
                  Enterprise / Business
                </button>
              </div>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">First Name</label>
                <input 
                  v-model="form.user.firstName" 
                  type="text" 
                  placeholder="e.g. Ibrahim" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>

              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Last Name</label>
                <input 
                  v-model="form.user.lastName" 
                  type="text" 
                  placeholder="e.g. Abubakar" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>
            </div>

            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Email Address</label>
              <input 
                v-model="form.user.email" 
                type="email" 
                placeholder="ibrahim@agribusiness.ng" 
                class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
              />
            </div>
          </div>

          <div class="space-y-4 pt-4 border-t border-gray-100">
            <h3 class="text-sm font-bold text-gray-900 uppercase tracking-wide border-l-4 border-indigo-600 pl-2">
              2. Core Survey Details
            </h3>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Business / Organization Name</label>
                <input 
                  v-model="form.organization" 
                  type="text" 
                  placeholder="e.g. Olam Agri Nigeria" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>

              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Business Sector</label>
                <select 
                  v-model="form.sector" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                >
                  <option value="Agro-Allied">Agro-Allied</option>
                  <option value="Agro-Processing">Agro-Processing</option>
                  <option value="AgTech">AgTech</option>
                  <option value="Agro-Industrial">Agro-Industrial</option>
                  <option value="FMCG & Logistics">FMCG & Logistics</option>
                </select>
              </div>
            </div>

            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Survey Title</label>
              <input 
                v-model="form.title" 
                type="text" 
                placeholder="e.g. Smallholder Farmer Yield & Grain Logistics 2026" 
                class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
              />
            </div>

            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Survey Description</label>
              <textarea 
                v-model="form.description" 
                rows="3" 
                placeholder="Briefly explain what participants will evaluate..." 
                class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition resize-none"
              ></textarea>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-2">
              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Date & Time Created</label>
                <input 
                  :value="form.createdAt" 
                  disabled 
                  type="text" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 bg-gray-50 text-gray-500 text-sm cursor-not-allowed"
                />
              </div>

              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Survey End Date</label>
                <input 
                  v-model="form.endDate" 
                  :disabled="form.isUnending" 
                  type="date" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition disabled:bg-gray-100 disabled:text-gray-400"
                />
                
                <div class="mt-2 flex items-center gap-2">
                  <input 
                    id="unending" 
                    v-model="form.isUnending" 
                    type="checkbox" 
                    class="rounded border-gray-300 text-indigo-600 focus:ring-indigo-500 h-4 w-4"
                  />
                  <label for="unending" class="text-xs text-gray-600 font-medium">Keep Survey Active (Unending)</label>
                </div>
              </div>
            </div>
          </div>

          <div class="space-y-4 pt-4 border-t border-gray-100">
            <h3 class="text-sm font-bold text-gray-900 uppercase tracking-wide border-l-4 border-indigo-600 pl-2">
              3. Target Demographics
            </h3>

            <div class="grid grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Minimum Age</label>
                <input 
                  v-model.number="form.minAge" 
                  type="number" 
                  min="18" 
                  max="100" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>
              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Maximum Age</label>
                <input 
                  v-model.number="form.maxAge" 
                  type="number" 
                  min="18" 
                  max="100" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>
            </div>

            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Location Coverage</label>
              <select 
                v-model="form.location" 
                class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
              >
                <option value="Nationwide (All States)">Nationwide (All Nigerian States)</option>
                <option value="Lagos State">Lagos State</option>
                <option value="Kano State">Kano State</option>
                <option value="Kaduna State">Kaduna State</option>
                <option value="Oyo State">Oyo State</option>
                <option value="Rivers State">Rivers State</option>
                <option value="FCT Abuja">FCT Abuja</option>
                <option value="Enugu State">Enugu State</option>
              </select>
            </div>

            <div>
              <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Monthly Income Bracket (LSM/SEC)</label>
              <select 
                v-model="form.incomeBracket" 
                class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
              >
                <option value="All Income Levels">All Income Bands</option>
                <option value="Under ₦50,000">Under ₦50,000 (Low SEC)</option>
                <option value="₦50,000 - ₦150,000">₦50,000 - ₦150,000 (Lower Middle SEC)</option>
                <option value="₦150,000 - ₦300,000">₦150,000 - ₦300,000 (Middle SEC)</option>
                <option value="₦300,000 - ₦500,000">₦300,000 - ₦500,000 (Upper Middle SEC)</option>
                <option value="Above ₦500,000">Above ₦500,000 (High SEC)</option>
              </select>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Education Level</label>
                <select 
                  v-model="form.educationLevel" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                >
                  <option value="All Education Levels">Any Education Level</option>
                  <option value="O'Level (WAEC/NECO)">O'Level (WAEC/NECO)</option>
                  <option value="OND/HND">OND / HND</option>
                  <option value="Bachelor's Degree">Bachelor's Degree</option>
                  <option value="Postgraduate/Master's">Postgraduate / Doctorate</option>
                </select>
              </div>

              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Employment Status</label>
                <select 
                  v-model="form.employmentStatus" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                >
                  <option value="All Employment Types">Any Employment Status</option>
                  <option value="Formal Corporate">Formal Corporate</option>
                  <option value="Informal / Trader">Informal / Trader / Farmer</option>
                  <option value="Student">Student</option>
                  <option value="NYSC Corp Member">NYSC Corp Member</option>
                  <option value="Unemployed">Unemployed</option>
                </select>
              </div>
            </div>
          </div>

          <div class="space-y-4 pt-4 border-t border-gray-100">
            <h3 class="text-sm font-bold text-gray-900 uppercase tracking-wide border-l-4 border-indigo-600 pl-2">
              4. Campaign Budget & Response Volume
            </h3>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Cost Per Response (₦)</label>
                <div class="relative">
                  <span class="absolute inset-y-0 left-0 pl-4 flex items-center text-gray-400 font-bold text-sm">₦</span>
                  <input 
                    v-model.number="form.costPerResponse" 
                    type="number" 
                    min="100" 
                    placeholder="500" 
                    class="w-full pl-9 pr-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                  />
                </div>
              </div>

              <div>
                <label class="block text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">Total Respondents Needed</label>
                <input 
                  v-model.number="form.totalRespondents" 
                  type="number" 
                  min="1" 
                  placeholder="100" 
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 text-gray-900 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                />
              </div>
            </div>

            <div class="p-4 bg-emerald-50 border border-emerald-200 rounded-xl flex items-center justify-between">
              <div>
                <p class="text-xs uppercase font-bold text-emerald-800 tracking-wider">Calculated Total Survey Budget</p>
                <p class="text-[11px] text-emerald-600">{{ form.totalRespondents || 0 }} Respondents × ₦{{ (form.costPerResponse || 0).toLocaleString() }}</p>
              </div>
              <div class="text-xl font-extrabold text-emerald-900">
                ₦{{ calculatedTotalBudget.toLocaleString() }}
              </div>
            </div>
          </div>

          <div class="space-y-4 pt-4 border-t border-gray-100">
            <div class="flex items-center justify-between">
              <h3 class="text-sm font-bold text-gray-900 uppercase tracking-wide border-l-4 border-indigo-600 pl-2">
                5. Survey Question Model
              </h3>
              <button 
                type="button" 
                @click="addQuestion"
                class="px-3 py-1.5 bg-indigo-50 hover:bg-indigo-100 text-indigo-600 font-semibold text-xs rounded-lg transition"
              >
                + Add Question
              </button>
            </div>

            <div v-for="(q, index) in form.questions" :key="q.id" class="p-4 rounded-xl border border-gray-200 bg-gray-50 space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-xs font-bold text-gray-700">Question {{ index + 1 }}</span>
                <button 
                  v-if="form.questions.length > 1" 
                  type="button" 
                  @click="removeQuestion(index)" 
                  class="text-xs text-red-500 font-semibold hover:underline"
                >
                  Remove
                </button>
              </div>

              <input 
                v-model="q.title" 
                type="text" 
                placeholder="Enter your question title here..." 
                class="w-full px-3 py-2 rounded-lg border border-gray-200 text-gray-900 text-xs bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500"
              />

              <div class="flex items-center gap-4 text-xs">
                <span class="font-medium text-gray-500">Selection Mode:</span>
                <label class="inline-flex items-center gap-1 cursor-pointer">
                  <input type="radio" :name="'type-' + q.id" value="single" v-model="q.selectionType" class="text-indigo-600" />
                  <span>Single Choice</span>
                </label>
                <label class="inline-flex items-center gap-1 cursor-pointer">
                  <input type="radio" :name="'type-' + q.id" value="multiple" v-model="q.selectionType" class="text-indigo-600" />
                  <span>Multiple Choice</span>
                </label>
              </div>

              <div class="space-y-2 pt-1">
                <p class="text-[11px] font-semibold text-gray-400 uppercase">Answer Options</p>
                <div v-for="(opt, optIdx) in q.options" :key="optIdx" class="flex items-center gap-2">
                  <span class="text-xs font-mono text-gray-400">{{ optIdx + 1 }}.</span>
                  <input 
                    v-model="q.options[optIdx]" 
                    type="text" 
                    placeholder="Option choice label" 
                    class="flex-1 px-3 py-1.5 rounded-lg border border-gray-200 text-xs bg-white focus:outline-none"
                  />
                  <button 
                    type="button" 
                    @click="removeOption(index, optIdx)" 
                    class="text-xs text-gray-400 hover:text-red-500 px-1"
                  >
                    ✕
                  </button>
                </div>
                <button 
                  type="button" 
                  @click="addOption(index)" 
                  class="text-xs text-indigo-600 font-semibold hover:underline pt-1 inline-block"
                >
                  + Add Option Choice
                </button>
              </div>
            </div>
          </div>

          <div class="pt-4">
            <a 
              href="/signup" 
              class="w-full py-4 px-6 bg-indigo-600 hover:bg-indigo-700 text-white text-base font-bold rounded-xl flex items-center justify-center gap-2 shadow-lg hover:shadow-indigo-200 transition-all duration-200 cursor-pointer block text-center"
            >
              <span>Create Survey & Continue</span>
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="w-5 h-5">
                <path fill-rule="evenodd" d="M3 10a.75.75 0 0 1 .75-.75h10.638L10.23 5.29a.75.75 0 1 1 1.04-1.08l5.5 5.25a.75.75 0 0 1 0 1.08l-5.5 5.25a.75.75 0 0 1 0 1.08l-5.5 5.25a.75.75 0 1 1-1.04-1.08l4.158-3.96H3.75A.75.75 0 0 1 3 10Z" clip-rule="evenodd" />
              </svg>
            </a>
            <p class="text-center text-xs text-gray-400 mt-2">
              You will be redirected to complete account verification to publish your survey.
            </p>
          </div>

        </form>
      </div>

      <div class="lg:col-span-5 lg:sticky lg:top-8 space-y-4">
        <div class="flex items-center justify-between px-1">
          <span class="text-xs font-bold uppercase tracking-wider text-gray-400">Live Participant Card Preview</span>
          <span class="inline-flex items-center gap-1 text-[11px] text-emerald-600 font-semibold">
            <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span> Dynamic Updates
          </span>
        </div>

        <div class="w-full bg-white rounded-2xl border border-gray-100 shadow-xl p-6 flex flex-col justify-between">
          <div>
            <div class="flex items-center justify-between mb-4">
              <div class="flex items-center gap-3">
                <div class="w-10 h-10 rounded-xl bg-emerald-700 flex items-center justify-center font-black text-xs text-white uppercase">
                  {{ avatarInitials }}
                </div>
                <div>
                  <h4 class="text-xs font-semibold text-gray-500">{{ form.organization || 'Enterprise Name' }}</h4>
                  <div class="flex items-center gap-1 text-[11px] text-emerald-600 font-medium">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="w-3.5 h-3.5">
                      <path fill-rule="evenodd" d="M10 18a8 8 0 1 0 0-16 8 8 0 0 0 0 16Zm3.857-9.809a.75.75 0 0 0-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 1 0-1.06 1.061l2.5 2.5a.75.75 0 0 0 1.137-.089l4-5.5Z" clip-rule="evenodd" />
                    </svg>
                    Verified {{ form.user.accountType }}
                  </div>
                </div>
              </div>
              <span class="px-2.5 py-1 text-[11px] font-medium bg-gray-100 text-gray-600 rounded-lg">
                {{ form.sector }}
              </span>
            </div>

            <h3 class="text-lg font-bold text-gray-900 mb-2 line-clamp-2">
              {{ form.title || 'Untitled Agribusiness Research Survey' }}
            </h3>
            <p class="text-sm text-gray-500 line-clamp-2 mb-6">
              {{ form.description || 'Provide a brief summary for participants explaining the core survey objectives...' }}
            </p>
          </div>

          <div>
            <div class="grid grid-cols-2 gap-3 py-3 px-4 bg-gray-50 rounded-xl mb-5">
              <div class="flex items-center gap-2">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.8" stroke="currentColor" class="w-5 h-5 text-emerald-600">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v12m-3-6h6m-7 6h8a2 2 0 0 0 2-2V8a2 2 0 0 0-2-2H7a2 2 0 0 0-2 2v8a2 2 0 0 0 2 2Z" />
                </svg>
                <div>
                  <p class="text-[10px] uppercase tracking-wider text-gray-400 font-medium">Payout / User</p>
                  <p class="text-sm font-bold text-gray-900">₦{{ (form.costPerResponse || 0).toLocaleString() }}</p>
                </div>
              </div>

              <div class="flex items-center gap-2">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.8" stroke="currentColor" class="w-5 h-5 text-indigo-500">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6l4 2-2 4m6-6a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z" />
                </svg>
                <div>
                  <p class="text-[10px] uppercase tracking-wider text-gray-400 font-medium">Expiration</p>
                  <p class="text-sm font-bold text-gray-900">{{ form.isUnending ? 'Unending' : (form.endDate || 'Ongoing') }}</p>
                </div>
              </div>
            </div>

            <button disabled class="w-full py-3 px-4 bg-indigo-600/80 text-white text-sm font-semibold rounded-xl flex items-center justify-center gap-2 cursor-not-allowed">
              Start Survey (Preview)
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="w-4 h-4">
                <path fill-rule="evenodd" d="M3 10a.75.75 0 0 1 .75-.75h10.638L10.23 5.29a.75.75 0 1 1 1.04-1.08l5.5 5.25a.75.75 0 0 1 0 1.08l-5.5 5.25a.75.75 0 1 1-1.04-1.08l4.158-3.96H3.75A.75.75 0 0 1 3 10Z" clip-rule="evenodd" />
              </svg>
            </button>
          </div>
        </div>

        <div class="p-5 bg-white border border-gray-100 rounded-2xl shadow-sm space-y-3">
          <h5 class="text-xs font-bold text-gray-900 uppercase tracking-wider">Demographic Criteria Summary</h5>
          
          <div class="grid grid-cols-2 gap-2 text-xs">
            <div>
              <span class="text-gray-400">Creator:</span> 
              <p class="font-semibold text-gray-700">{{ form.user.firstName || 'User' }} {{ form.user.lastName }}</p>
            </div>
            <div>
              <span class="text-gray-400">Age Range:</span> 
              <p class="font-semibold text-gray-700">{{ form.minAge }} - {{ form.maxAge }} yrs</p>
            </div>
            <div>
              <span class="text-gray-400">Location:</span> 
              <p class="font-semibold text-gray-700">{{ form.location }}</p>
            </div>
            <div>
              <span class="text-gray-400">Income SEC:</span> 
              <p class="font-semibold text-gray-700">{{ form.incomeBracket }}</p>
            </div>
            <div>
              <span class="text-gray-400">Education:</span> 
              <p class="font-semibold text-gray-700">{{ form.educationLevel }}</p>
            </div>
            <div>
              <span class="text-gray-400">Employment:</span> 
              <p class="font-semibold text-gray-700">{{ form.employmentStatus }}</p>
            </div>
          </div>
          
          <div class="pt-2 border-t border-gray-100 flex items-center justify-between text-xs">
            <span class="text-gray-400">Questions Attached:</span>
            <span class="font-bold text-indigo-600">{{ form.questions.length }} Question(s)</span>
          </div>
        </div>

      </div>

    </div>
  </section>
</template>

<script setup>
import { reactive, computed } from 'vue'

// Current timestamp formatting
const currentDateTime = new Date().toLocaleString('en-NG', { 
  dateStyle: 'medium', 
  timeStyle: 'short' 
})

// Comprehensive reactive state binding for all requested models
const form = reactive({
  user: {
    firstName: '',
    lastName: '',
    email: '',
    accountType: 'Business'
  },
  organization: '',
  sector: 'Agro-Allied',
  title: '',
  description: '',
  minAge: 18,
  maxAge: 65,
  location: 'Nationwide (All States)',
  incomeBracket: 'All Income Levels',
  educationLevel: 'All Education Levels',
  employmentStatus: 'All Employment Types',
  costPerResponse: 500,
  totalRespondents: 100,
  createdAt: currentDateTime,
  endDate: '',
  isUnending: false,
  questions: [
    {
      id: 1,
      title: 'How do you source crop protection materials?',
      selectionType: 'single', // 'single' or 'multiple'
      options: ['Direct Wholesaler', 'Local Open Market', 'Agtech Platform']
    }
  ]
})

// Calculated Field: Total Budget = Cost per response * Total Respondents Needed
const calculatedTotalBudget = computed(() => {
  const cost = Number(form.costPerResponse) || 0
  const count = Number(form.totalRespondents) || 0
  return cost * count
})

// Avatar initials generator
const avatarInitials = computed(() => {
  if (form.organization) {
    const words = form.organization.trim().split(' ')
    if (words.length >= 2) return (words[0][0] + words[1][0]).toUpperCase()
    return form.organization.substring(0, 3).toUpperCase()
  }
  if (form.user.firstName) {
    return (form.user.firstName[0] + (form.user.lastName[0] || '')).toUpperCase()
  }
  return 'NEW'
})

// Dynamic Question Builder Helper Functions
const addQuestion = () => {
  form.questions.push({
    id: Date.now(),
    title: '',
    selectionType: 'single',
    options: ['Option 1', 'Option 2']
  })
}

const removeQuestion = (qIndex) => {
  form.questions.splice(qIndex, 1)
}

const addOption = (qIndex) => {
  form.questions[qIndex].options.push('')
}

const removeOption = (qIndex, optIndex) => {
  if (form.questions[qIndex].options.length > 1) {
    form.questions[qIndex].options.splice(optIndex, 1)
  }
}
</script>