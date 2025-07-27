<template>
  <div :class="[
      'bg-gray-900 text-white h-screen transition-all duration-300 fixed top-0 left-0 z-50',
      collapsed ? 'w-20' : 'w-64'
    ]"
  >
    <div class="flex items-center justify-between p-4">
      <span v-if="!collapsed" class="font-bold text-lg">ZED Panel</span>
      <button @click="$emit('toggle')" class="focus:outline-none">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16" />
        </svg>
      </button>
    </div>
    <ul class="space-y-2 mt-4">
      <li
        @click="$emit('navigate', 'dashboard')"
        class="hover:bg-gray-700 rounded px-4 py-2 cursor-pointer"
      >
        <span v-if="!collapsed">📊 Dashboard</span>
        <span v-else title="Dashboard">📊</span>
      </li>
      <li
        @click="$emit('navigate', 'addRecord')"
        class="hover:bg-gray-700 rounded px-4 py-2 cursor-pointer"
      >
        <span v-if="!collapsed">📝 Add Record</span>
        <span v-else title="Add Record">📝</span>
      </li>
    </ul>
  </div>
</template>

<script setup>
defineProps(['collapsed'])
</script>
