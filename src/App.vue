<template>
  <div class="min-h-screen flex bg-gray-100">
    <Sidebar :collapsed="sidebarCollapsed" @toggle="toggleSidebar" @navigate="navigateTo" />
    <div :class="[sidebarCollapsed ? 'ml-20' : 'ml-64', 'transition-all duration-300 flex-1 p-6']">
      <Dashboard v-if="currentPage === 'dashboard'" />
      <AddRecordForm v-else-if="currentPage === 'addRecord'" />
    </div>
  </div>
</template>

<script setup>
import Sidebar from './components/Sidebar.vue'
import Dashboard from './components/Dashboard.vue'
import AddRecordForm from './components/AddRecordForm.vue'
import { ref } from 'vue'

const sidebarCollapsed = ref(false)
const currentPage = ref('dashboard')

function toggleSidebar() {
  sidebarCollapsed.value = !sidebarCollapsed.value
}

function navigateTo(page) {
  currentPage.value = page
}
</script>
