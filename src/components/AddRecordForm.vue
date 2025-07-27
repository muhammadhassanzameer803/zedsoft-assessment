<template>
  <div class="bg-white p-6 rounded-lg shadow">
    <h1 class="text-2xl font-bold text-gray-800 mb-4">Add New Record</h1>
    <form class="space-y-4">
      <input type="text" placeholder="Name" class="w-full p-2 border rounded" />
      <input type="date" class="w-full p-2 border rounded" />
      <textarea placeholder="Case Description" class="w-full p-2 border rounded"></textarea>
      <button type="submit" class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded">
        Submit
      </button>
    </form>
  </div>
</template>
