<script setup>

</script>

<template>
  <div class="bg-image">
    <div class="header">
      <div class="header-content">
        <h1>Start streaming the most popular movies on FreeFlix</h1>
        <p>Sign up to start watching your first movie!</p>
        <form class="email-signup">
          <input type="email" placeholder="Email address" required />
          <button type="submit">Watch Now</button>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>

.bg-image {
    background-image: linear-gradient(rgba(78, 25, 20, 0.7),rgba(78,25,20,0.7)),url('/src/assets/Background.png');
    font-size: 20px;
    text-align: center;
    margin: 0;
    padding: 0;
    min-height: 100vh;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    flex-direction: column;
    height: 100%;
    width: 100%;
    justify-content: center;
    align-items: center;
}


.header {
    width: 100%;
    height: calc(100vh - 200px); 
    display: flex;
    flex-direction: column;
    justify-content: center; 
    align-items: center;
    text-align: center;
}

.header-content {
    padding: 20px;
    background: rgba(0, 0, 0, 0.8); 
    border-radius: 15px; 
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5); 
}


.header-content h1 {
    font-family: 'Poppins', sans-serif; 
    font-size: 2.5rem; 
    color: white; 
    margin-bottom: 20px;
    text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8); 
}


.header-content p {
    font-family: 'Roboto', sans-serif;
    font-size: 1.2rem;
    color: #ffffff;
    margin-bottom: 20px;
}


.email-signup {
    display: flex;
    justify-content: center; 
    align-items: center; 
    margin-top: 20px;
}

.email-signup input {
    width: 300px;
    padding: 12px;
    border-radius: 5px;
    border: 1px solid rgba(255, 255, 255, 0.5);
    background: rgba(255, 255, 255, 0.1);
    color: #fff;
}

.email-signup button {
    padding: 12px 20px;
    border-radius: 5px;
    background: #87CEEB; 
    color: #fff;
    border: none;
    cursor: pointer;
    margin-left: 10px; 
    transition: background-color 0.3s, transform 0.2s; 
}

.email-signup button:hover {
    background: #6BB5E3; 
}
</style>
