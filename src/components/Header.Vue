<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
  <div class="header">
    <nav>
      <ul class="nav">
        <li class="logo">FreeFlix</li>
        <div class="buttons">
          <li><RouterLink to="/register" class="button sign-up">Sign up</RouterLink></li>
          <li><RouterLink to="/login" class="button login">Login</RouterLink></li>
        </div>
      </ul>
    </nav>
    <div class="header-content">
      <h1 class="page-title">Welcome to FreeFlix</h1>
    </div>
  </div>
</template>

<style scoped>
.header {
    width: 100%;
    height: calc(100vh - 200px); 
    display: flex;
    flex-direction: column;
    justify-content: center; 
    align-items: center;
    text-align: center;
}

nav {
    display: flex;
    justify-content: space-between;
    width: 100%;
    padding: 20px;
}

nav .logo {
    font-size: 2rem;
    color: #ffffff;
    font-family: 'Poppins', sans-serif;
}

nav .buttons {
    display: flex;
    gap: 15px;
}

nav .button {
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

nav .button:hover {
    background-color: #c876d3;
    transform: scale(1.1);
}

.header-content {
    padding: 20px;
    background: rgba(0, 0, 0, 0.8);
    border-radius: 15px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
}

.page-title {
    font-family: 'Poppins', sans-serif;
    font-size: 3.5em;
    color: white;
    margin: 20px 0;
    text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8);
}
</style>
