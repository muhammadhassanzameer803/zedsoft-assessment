<template>
  <div>
    <h1 class="text-3xl font-bold text-gray-800 mb-6">Dashboard</h1>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-6">
      <div class="bg-white p-6 rounded-lg shadow hover:shadow-xl transition-shadow duration-300">
        <h2 class="text-lg font-semibold text-gray-800">Total Records</h2>
        <p class="text-2xl mt-2 font-bold text-blue-600">1,240</p>
      </div>
      <div class="bg-white p-6 rounded-lg shadow hover:shadow-xl transition-shadow duration-300">
        <h2 class="text-lg font-semibold text-gray-800">Active Cases</h2>
        <p class="text-2xl mt-2 font-bold text-green-600">312</p>
      </div>
      <div class="bg-white p-6 rounded-lg shadow hover:shadow-xl transition-shadow duration-300">
        <h2 class="text-lg font-semibold text-gray-800">Closed Files</h2>
        <p class="text-2xl mt-2 font-bold text-red-600">928</p>
      </div>
    </div>

    <div class="bg-white p-6 rounded-lg shadow">
      <h2 class="text-xl font-semibold mb-4">Recent Activity</h2>
      <ul class="space-y-2">
        <li class="border-b pb-2">📝 Record 2025-A added on 26 July</li>
        <li class="border-b pb-2">📁 Case X928 closed by Judge A</li>
        <li class="border-b pb-2">🧾 Form submitted by Clerk Z</li>
      </ul>
    </div>
  </div>
</template>
