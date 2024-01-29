<script setup>
  const { image, name, occupation } = defineProps([
  'image',
  'name',
  'occupation',
]);
</script>


<template>
    <NCard>
    <template #cover>
      <img :src="image" />
    </template>
    <h3>{{ name }}</h3>
    <slot></slot>
  </NCard>
</template>


<style scoped>
  
.n-card {
  width: 200px;
  margin: 15px 20px;
  height: 350px;
}
.n-card img {
  height: 250px;
  object-fit: cover;
}

.n-card h3 {
  margin-top: 14px;
}

p {
  font-size: 10px;
}

@media (max-width: 600px) {
   
.n-card {
  width: 150px;
  margin: 15px 20px;
  height: 300px;
}
.n-card img {
  max-height: 250px;
  height: 200px;
  object-fit: cover;
}

.n-card h3 {
  margin-top: 14px;
}

p {
  font-size: 10px;
}
}


</style>