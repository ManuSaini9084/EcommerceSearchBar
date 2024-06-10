<template>
  <div>
    <NavbarComponent @search-category="onCategorySearch" />
    <div class="max-w-xl mx-auto mt-10">
      <input
        v-model="query"
        @input="onInput"
        class="w-full p-2 border border-gray-300 rounded"
        type="text"
        placeholder="Search for clothes..."
      />
      <div v-if="results.length" class="mt-4">
        <div
          v-for="item in results"
          :key="item.id"
          class="p-4 border-b border-gray-200 flex"
        >
          <img :src="item.imageUrl" alt="item.name" class="w-24 h-24 object-cover mr-4"/>
          <div>
            <h2 class="text-lg font-bold">{{ item.name }}</h2>
            <p class="text-gray-600">{{ item.description }}</p>
            <p class="text-sm text-gray-500">Price: {{ item.price }}</p>
            <p class="text-sm text-gray-500">Sizes: {{ item.size }}</p>
            <p class="text-sm text-gray-500">Colors: {{ item.color }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NavbarComponent from './NavbarComponent.vue';

export default {
  components: {
    NavbarComponent
  },
  data() {
    return {
      query: '',
      results: []
    };
  },
  methods: {
    onInput() {
      if (this.query.length > 3) {
        fetch(`http://localhost:3000/search?q=${this.query}`)
          .then(response => response.json())
          .then(data => {
            this.results = data;
          });
      } else {
        this.results = [];
      }
    },
    onCategorySearch(category) {
      this.query = category;
      this.onInput();
    }
  }
};
</script>

<style scoped>
/* Add any scoped styles here */
</style>
