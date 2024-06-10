<template>
    <nav class="bg-white shadow-md p-4">
      <div class="container mx-auto flex justify-center items-center">
        <ul class="flex space-x-8">
          <li>
            <a href="#" @click.prevent="searchCategory('T-Shirt')" class="text-gray-800 hover:text-gray-600 transition duration-200">T-Shirts</a>
          </li>
          <li>
            <a href="#" @click.prevent="searchCategory('Jeans')" class="text-gray-800 hover:text-gray-600 transition duration-200">Jeans</a>
          </li>
          <li>
            <a href="#" @click.prevent="searchCategory('Jacket')" class="text-gray-800 hover:text-gray-600 transition duration-200">Jackets</a>
          </li>
          <li>
            <a href="#" @click.prevent="searchCategory('Sweater')" class="text-gray-800 hover:text-gray-600 transition duration-200">Sweaters</a>
          </li>
          <li>
            <a href="#" @click.prevent="searchCategory('Dress')" class="text-gray-800 hover:text-gray-600 transition duration-200">Dresses</a>
          </li>
        </ul>
      </div>
    </nav>
  </template>
  
  <script>
  export default {
    name: 'NavbarComponent',
    methods: {
      searchCategory(category) {
        this.$emit('search-category', category);
      }
    }
  };
  </script>
  
  <style scoped>
  /* Add any scoped styles here */
  </style>
  