<template>
    <button class="form-btn" @click="enviarForm" :class="{ 'btn-deshabilitado': !validarForm }">Enviar</button>
  </template>
  
  <script lang="ts">
  import { ref } from 'vue';
  
  export default {
    props: {
      validarForm: Boolean,
      //Creo la variable validarForm y lo asigno como tipo boolean
    },
    setup(props) {
      const enviarForm = () => {
        if (props.validarForm) {//Si es true, ejecuta el mensaje
          alert('¡Formulario enviado con éxito!')
          //Cuando el botón se accione me mandará este mensaje
          //Solo podrá activarse el botón al cumplirse todas las validaciones
        }
      };
  
      return {
        enviarForm,
      };
    },
  };
  </script>
  
  <style scoped>
  .form-btn {
    padding: 15px;
    background-color: cadetblue;
    color: white;
    border: 0;
    outline: 0;
    cursor: pointer;
    transition: background-color 0.3s ease, color 0.3s ease;
  }
  
  .form-btn:hover {
    background-color: white;
    color: cadetblue;
  }
  
  .btn-deshabilitado {
    background-color: lightgray;
    color: gray;
    cursor: not-allowed;
  }
  </style>
  