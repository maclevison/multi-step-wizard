<script setup>
import { ref, computed } from 'vue';
import BasicInfo from './steps/BasicInfo.vue';
import CompanyInfo from './steps/CompanyInfo.vue';
import Goals from './steps/Goals.vue';
import Communication from './steps/Communication.vue';
import Summary from './steps/Summary.vue';

const step = ref(1);
const formData = ref({
  name: '',
  email: '',
  companySize: '',
  role: '',
  goals: '',
  preferredContact: ''
});

const nextStep = () => {
  if (step.value < 5) step.value++;
};

const prevStep = () => {
  if (step.value > 1) step.value--;
};

const completeOnboarding = () => {
  alert('Onboarding complete!');
};

const currentComponent = computed(() => {
  switch (step.value) {
    case 1: return BasicInfo;
    case 2: return CompanyInfo;
    case 3: return Goals;
    case 4: return Communication;
    case 5: return Summary;
  }
});

const updateFormData = (field, value) => {
  formData.value[field] = value;
};
</script>

<template>
  <div class="max-w-2xl mx-auto p-6 space-y-6">
    <div class="space-y-2">
      <h1 class="text-3xl font-bold">Welcome to Our Platform</h1>
      <p class="text-gray-600">Let's get you set up in just a few steps.</p>
    </div>
    
    <div class="flex justify-between mb-4 gap-1">
      <div 
        v-for="i in 5" 
        :key="i" 
        :class="[
          'w-1/5 h-2 rounded', 
          i <= step ? 'bg-blue-500' : 'bg-gray-200'
        ]"
      ></div>
    </div>

    <component 
      :is="currentComponent" 
      :form-data="formData" 
      @update="updateFormData"
    />

    <div class="flex justify-between pt-4">
      <button 
        v-if="step > 1" 
        @click="prevStep" 
        class="px-4 py-2 border rounded text-gray-700 hover:bg-gray-100"
      >
        Previous
      </button>
      <button 
        v-if="step < 5" 
        @click="nextStep" 
        class="ml-auto px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600"
      >
        Next
      </button>
      <button 
        v-else 
        @click="completeOnboarding" 
        class="ml-auto px-4 py-2 bg-green-500 text-white rounded hover:bg-green-600"
      >
        Complete
      </button>
    </div>
  </div>
</template>