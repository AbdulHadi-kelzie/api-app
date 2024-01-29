<script setup>
  import TheHeader from './components/UI/TheHeader.vue';
  import Cards from './components/UI/Cards.vue';
  

</script>


<template>
  <div class="container">
    <TheHeader />
    <Cards />
  </div>
</template>


<style scoped>
  .container{
    max-width: 1080px;
    margin: 0 auto;
  }
</style>