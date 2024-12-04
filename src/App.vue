<script setup>
import axios from "axios";
import { ref, onMounted } from 'vue';
import { useRouter } from "vue-router";

const props = defineProps(["genres"]);
const router = useRouter();
const selectedGenre = ref(28);
const response = ref(null);

const genres = [ 
  { id: 12, genreName: 'Adventure' },
  {id: 16, genreName: 'Animation' },
  {id: 35, genreName: 'Comedy' },
  {id: 10402, genreName: 'Music' },
  {id: 878, genreName: 'Sci-Fi' },
];

async function getMovieByGenre() {
  response.value = await axios.get(`https://api.themoviedb.org/3/discover/movie?api_key=${import.meta.env.VITE_TMDB_KEY}&include_adult=false&with_genres=${selectedGenre.value}`);
}

function getMovieDetails(id) {
  router.push(`/movies/${id}`)
}

onMounted(async () => {
  response.value = await axios.get(`https://api.themoviedb.org/3/discover/movie?api_key=${import.meta.env.VITE_TMDB_KEY}&include_adult=false&with_genres=${selectedGenre.value}`);
})
</script>

<template>
  <div class="movie-gallery">
    <select v-model="selectedGenre" @change="getMovieByGenre()">
      <option v-for="genre of genres" :value="genre.id">{{ genre.genreName }}</option>
    </select>
    <div v-if="response" class="movie-list">
      <div v-for="movie in response.data.results" :key="movie.id" class="movie-card" @click="getMovieDetails(movie.id)">
        <img :src="`https://image.tmdb.org/t/p/w500${movie.poster_path}`" alt="Movie Poster" class="movie-poster" />
        <p class="movie-title">{{ movie.title }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
nav {
    display: flex;
    align-items: center; 
    justify-content: space-between; 
    padding: 10px; 
    position: absolute; 
    width: 100%; 
}

nav img.logo {
    height: 60px; 
    margin-left: 20px; 
}

.nav-buttons {
    display: flex; 
    gap: 15px; 
    margin-right: 20px; 
}

nav button {
    background-color: #87CEEB; 
    color: white; 
    border: none;
    border-radius: 5px; 
    padding: 10px 15px; 
    cursor: pointer;
    transition: background-color 0.3s, transform 0.2s; 
    font-family: 'Poppins', sans-serif; 
    font-size: 1em; 
}

nav button:hover {
    background-color: #c876d3; 
    transform: scale(1.1); 
}
</style>