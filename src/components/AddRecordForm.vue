<template>
  <div class="bg-white p-6 rounded-lg shadow max-w-2xl mx-auto">
    <!-- Progress Bar -->
    <div class="flex mb-6">
      <div
        v-for="n in 3"
        :key="n"
        class="flex-1 h-2 mx-1 rounded-full"
        :class="{
          'bg-green-500': currentStep >= n,
          'bg-gray-300': currentStep < n
        }"
      ></div>
    </div>
    
<component
  :is="currentComponent"
  v-bind="form"
  :errors="errors"
  @update:fullName="form.fullName = $event"
  @update:date="form.date = $event"
  @update:dob="form.dob = $event"
  @update:caseNumber="form.caseNumber = $event"
  @update:caseDetails="form.caseDetails = $event"
  @update:sealDescription="form.sealDescription = $event"
  @update:file="form.file = $event"
  @next="nextStep"
  @prev="prevStep"
  @submit="submitForm"
/>


  </div>
</template>

<script setup>
import { ref, reactive, computed } from 'vue'
import AddRecordStep1 from './AddRecordStep1.vue'
import AddRecordStep2 from './AddRecordStep2.vue'
import AddRecordStep3 from './AddRecordStep3.vue'

const currentStep = ref(1)

const form = reactive({
  fullName: '',
  date: '',
  dob: '',
  caseNumber: '',
  caseDetails: '',
  sealDescription: '',
  file: null,
})

const errors = reactive({})

// Step switching
const nextStep = () => {
  if (validateStep(currentStep.value)) {
    currentStep.value++
  }
}

const prevStep = () => {
  if (currentStep.value > 1) currentStep.value--
}

// Final submit
const submitForm = () => {
  if (validateStep(3)) {
    alert("Form submitted successfully! Check console for data.")
    console.log(JSON.stringify(form, null, 2))
  }
}

// Validation logic
function validateStep(step) {
  Object.keys(errors).forEach((key) => (errors[key] = '')) // clear

  if (step === 1) {
    if (!form.fullName) errors.fullName = "Name is required"
    if (!form.date) errors.date = "Date is required"
    if (!form.dob) errors.dob = "DOB is required"
  } else if (step === 2) {
    if (!form.caseNumber) errors.caseNumber = "Case Number required"
    if (!form.caseDetails) errors.caseDetails = "Case Details required"
  } else if (step === 3) {
    if (!form.sealDescription) errors.sealDescription = "Seal description required"
  }

  return Object.values(errors).every((e) => !e)
}

const currentComponent = computed(() => {
  switch (currentStep.value) {
    case 1: return AddRecordStep1
    case 2: return AddRecordStep2
    case 3: return AddRecordStep3
  }
})
</script>
