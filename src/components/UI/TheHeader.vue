<script setup>
  
</script>


<template>
  <header id="header">
    <h1>The Rick and Morty API</h1>
  </header>
  
</template>


<style scoped>
  
  header {
    height: 30vh;
    padding: 20px;

    display: flex;
    justify-content: center;
    align-items: flex-end;

    background-image: url('https://images7.alphacoders.com/133/1335145.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    
    
  }

  header h1 {
    font-size: 2rem;
    font-weight: bold;
    color: black;
    padding: 8px 10px;
    background-color: white;
    border-radius: 8px;
  }

  @media (max-width: 800px) {
    header h1 {
    font-size: 1.5rem;
    font-weight: bold;
    color: black;
    padding: 8px 10px;
    background-color: white;
    border-radius: 8px;
  }
  }


  @media (max-width: 600px) {
    header h1 {
    font-size: 1.25rem;
    font-weight: bold;
    color: black;
    padding: 8px 10px;
    background-color: white;
    border-radius: 8px;
  }
  }
  
</style>