<script setup>
import axios from "axios";
import { ref, onMounted } from 'vue';

const response = ref(null);
const numbers = ref([]);

// Random 3 numbers using a Set
numbers.value = (() => {
  const set = new Set();

  while (true) {
    set.add(Math.floor(Math.random() * 19));

    if (set.size === 3) {
      return set;
    }
  }
})();

onMounted(async () => {
  response.value = await axios.get(`https://api.themoviedb.org/3/movie/now_playing?api_key=${import.meta.env.VITE_TMDB_KEY}`);
})
</script>

<template>
  <div class="movie-gallery">
    <div v-if="response" class="movie-list">
      <div v-for="number in numbers" :key="response.data.results[number].id" class="movie-card">
        <img :src="`https://image.tmdb.org/t/p/w500${response.data.results[number].poster_path}`" alt="Movie Poster" class="movie-poster" />
        <p class="movie-title">{{ response.data.results[number].title }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped></style>

<style>
.movie-container {
  display: flex;
  justify-content: space-evenly;
  gap: 10px;
  margin-top: 20px;
  margin-bottom: 20px;
}

.movie-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 300px;
  text-align: center;
}

.movie-poster {
  width: 100% !important; 
  height: auto !important; /*need to fix at some point */
  object-fit: cover;
}

.movie-title {
  font-size: 1rem;
  color: hotpink;
  margin-top: 10px;
}

.text {
  margin-top: 20px;
  font-size: 24px;
  text-align: center;
  font-weight: bold;
}
</style>





  
  
  