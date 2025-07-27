<template>
  <div>
    <h2 class="text-xl font-bold mb-4">Step 2: Judicial Case References</h2>
    <form class="space-y-4">
      <div>
        <input
          :value="caseNumber"
          @input="$emit('update:caseNumber', $event.target.value)"
          type="text"
          placeholder="Case Number"
          class="w-full p-2 border rounded"
        />
        <p class="text-red-500 text-sm" v-if="errors.caseNumber">{{ errors.caseNumber }}</p>
      </div>

      <div>
        <textarea
          :value="caseDetails"
          @input="$emit('update:caseDetails', $event.target.value)"
          placeholder="Case Details"
          class="w-full p-2 border rounded"
        ></textarea>
        <p class="text-red-500 text-sm" v-if="errors.caseDetails">{{ errors.caseDetails }}</p>
      </div>

      <div class="flex gap-2">
        <button @click.prevent="$emit('prev')" class="bg-gray-500 text-white px-4 py-2 rounded hover:bg-gray-600">
          Back
        </button>
        <button @click.prevent="$emit('next')" class="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700">
          Next
        </button>
      </div>
    </form>
  </div>
</template>

<script setup>
defineProps(['caseNumber', 'caseDetails', 'errors'])
defineEmits(['update:caseNumber', 'update:caseDetails', 'next', 'prev'])
</script>
