<template>
    <div class="form-fields">
      <h3>Nombre</h3>
      <input type="text" v-model="nombre">
      <span v-if="!validarNombre" style="color: red;">Por favor, ingresa un nombre válido (máximo 18 caracteres).</span>
  
      <h3>Apellido</h3>
      <input type="text" v-model="apellido">
      <span v-if="!validarApellido" style="color: red;">Por favor, ingresa un apellido válido (máximo 18 caracteres).</span>
  
      <h3>Edad</h3>
      <select v-model="edad">
        <option v-for="age in rangoEdad" :key="age" :value="age">{{ age }}</option>
      </select>
  
      <h3>Género</h3>
      <select v-model="genero">
        <option value="masculino">Masculino</option>
        <option value="femenino">Femenino</option>
      </select>
  
      <h3>Número de teléfono</h3>
      <input type="text" v-model="telefono">
      <span v-if="!validarTelefono" style="color: red;">Por favor, ingresa un número de teléfono válido (10 dígitos).</span>
  
      <div class="form-btn-container">
        <BtnForm :validarForm="validarForm" />
      </div>
    </div>
  </template>
  
  
  <script setup lang="ts">
  import BtnForm from './BtnForm.vue';
  import { ref, computed } from 'vue';
  
  const nombre = ref('');
  const apellido = ref('');
  const rangoEdad = Array.from({ length: 61 }, (_, i) => i);
  const edad = ref('0');
  const genero = ref('masculino');
  const telefono = ref('');
  
  const validarNombre = computed(() => /^[a-zA-ZáéíóúÁÉÍÓÚüÜñÑ\s]{1,18}$/.test(nombre.value));
  const validarApellido = computed(() => /^[a-zA-ZáéíóúÁÉÍÓÚüÜñÑ\s]{1,18}$/.test(apellido.value));
  const validarTelefono = computed(() => /^[0-9]{10}$/.test(telefono.value));
  const validarForm = computed(() => validarNombre.value && validarApellido.value && validarTelefono.value);
  
  // Validar que nombre y apellido sean distintos
  const validarNombresDiferentes = computed(() => nombre.value.toLowerCase() !== apellido.value.toLowerCase());
  </script>
  
  <style scoped>
  .form-fields {
    display: flex;
  flex-direction: column;
  align-items: center;
  width: 400px; /* Ajusta el ancho del formulario según tus necesidades */
  border-radius: 15px;
  padding: 20px; /* Ajusta el relleno del formulario según tus necesidades */
  margin: 10px;
  border: 1px solid #ccc;
  }
  
  .form-btn-container {
    margin-top: 20px;
    width: 100%;
    display: flex;
    justify-content: center;
  }
  </style>
  