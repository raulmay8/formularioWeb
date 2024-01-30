<template>
  <div class="home-container">
    <HomeView />
  </div>
</template>

<script setup lang="ts">
import HomeView from './views/HomeView.vue';
</script>

<style scoped>
.home-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh; /* Ajusta la altura según tus necesidades */
}
</style>
