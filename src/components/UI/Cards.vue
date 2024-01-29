<script setup>
import TheCard from '../TheCard.vue';
import axios from 'axios';
import { ref, watch, onMounted } from 'vue';

const characters = ref(null);
const page = ref(1);

onMounted(async () => {
  const response = await axios.get('https://rickandmortyapi.com/api/character');
  characters.value = response.data.results;
});

watch(page, async () => {
  const res = await axios.get(
    `https://rickandmortyapi.com/api/character/?page=${page.value}`
  );
  characters.value = res.data.results;
});

const scrollToTop  = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  });
}

</script>

<template>
  <div id="container" class="container">
    <div class="cards">
      <TheCard
        v-for="character in characters"
        :key="character.char_id"
        :image="character.image"
        :name="character.name"
        ><p>{{ character.location.name }}</p></TheCard
      >
    </div>
    <div class="button-container">
      <button @click="page--; scrollToTop()">&lt</button>
      <button @click="page++; scrollToTop()">></button>
    </div>
  </div>
</template>

<style scoped>

.container {
  background-color: rgb(27, 26, 26);
  padding: 30px;
  height: 100%;
}
.cards {
  max-width: 1000px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  height: auto;
}
.cards h3 {
  font-weight: bold;
}
.cards p {
  font-size: 10px;
}

.button-container {
  display: flex;
  justify-content: center;
  padding-top: 30px;
}
.button-container button {
  border: none;
  width: 50px;
  height: 50px;
  border-radius: 100%;
  margin: 0 5px;
  cursor: pointer;
}

</style>
