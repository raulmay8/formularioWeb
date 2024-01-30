<template>
    <div class="form-container">
      <h1 class="title">Mi Formulario</h1>
      <CamposForm />
    </div>
  </template>
  
  <script setup lang="ts">
  import CamposForm from './CamposForm.vue';
  </script>
  
  <style scoped>
  .form-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh; /* Ajusta la altura según tus necesidades */
  }
  
  .title {
    font-size: 24px;
    margin-bottom: 20px;
  }
  </style>