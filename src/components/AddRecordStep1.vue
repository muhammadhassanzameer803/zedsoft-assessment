<template>
  <div>
    <h2 class="text-xl font-bold mb-4">Step 1: Basic Information</h2>
    <form class="space-y-4">
      <div>
        <input
          :value="fullName"
          @input="$emit('update:fullName', $event.target.value)"
          type="text"
          placeholder="Full Name"
          class="w-full p-2 border rounded"
        />
        <p class="text-red-500 text-sm" v-if="errors.fullName">{{ errors.fullName }}</p>
      </div>

      <div>
        <input
          :value="date"
          @input="$emit('update:date', $event.target.value)"
          type="date"
          class="w-full p-2 border rounded"
        />
        <p class="text-red-500 text-sm" v-if="errors.date">{{ errors.date }}</p>
      </div>

      <div>
        <input
          :value="dob"
          @input="$emit('update:dob', $event.target.value)"
          type="text"
          placeholder="Date of Birth"
          class="w-full p-2 border rounded"
        />
        <p class="text-red-500 text-sm" v-if="errors.dob">{{ errors.dob }}</p>
      </div>

      <button @click.prevent="$emit('next')" class="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700">
        Next
      </button>
    </form>
  </div>
</template>

<script setup>
defineProps(['fullName', 'date', 'dob', 'errors'])
defineEmits(['update:fullName', 'update:date', 'update:dob', 'next'])
</script>
