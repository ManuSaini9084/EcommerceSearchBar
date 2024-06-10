<template>
    <div class="max-w-6xl mx-auto mt-10 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
      <div
        v-for="item in items"
        :key="item.id"
        class="bg-white shadow-md rounded-lg overflow-hidden"
      >
        <img :src="item.imageUrl" :alt="item.name" class="w-full h-48 object-cover" />
        <div class="p-4">
          <h2 class="text-lg font-bold">{{ item.name }}</h2>
          <p class="text-gray-600">{{ item.description }}</p>
          <p class="text-sm text-gray-500">Price: {{ item.price }}</p>
          <p class="text-sm text-gray-500">Sizes: {{ item.size }}</p>
          <p class="text-sm text-gray-500">Colors: {{ item.color }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      items: {
        type: Array,
        required: true
      }
    }
  };
  </script>
  
  <style scoped>
  /* Add any scoped styles here */
  </style>
  