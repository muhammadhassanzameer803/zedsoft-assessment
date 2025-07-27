<template>
  <div>
    <h2 class="text-xl font-bold mb-4">Step 3: Seals and Sample Entry</h2>
    <form class="space-y-4">
      <div>
        <input type="file" @change="handleFile" class="w-full p-2 border rounded" />
      </div>

      <div>
        <textarea
          :value="sealDescription"
          @input="$emit('update:sealDescription', $event.target.value)"
          placeholder="Seal Description"
          class="w-full p-2 border rounded"
        ></textarea>
        <p class="text-red-500 text-sm" v-if="errors.sealDescription">{{ errors.sealDescription }}</p>
      </div>

      <div class="flex gap-2">
        <button @click.prevent="$emit('prev')" class="bg-gray-500 text-white px-4 py-2 rounded hover:bg-gray-600">Back</button>
        <button @click.prevent="$emit('submit')" class="bg-green-600 text-white px-4 py-2 rounded hover:bg-green-700">Submit</button>
      </div>
    </form>
  </div>
</template>

<script setup>
defineProps(['sealDescription', 'errors'])
const emit = defineEmits(['update:sealDescription', 'update:file', 'prev', 'submit'])

function handleFile(event) {
  emit('update:file', event.target.files[0])
}
</script>
