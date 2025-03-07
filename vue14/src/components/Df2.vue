<script setup>
import { ref } from "vue";

// Inicializando a variável de idade
const idade = ref(null);
</script>

<template>
  <label for="registroUsuario">
    <input type="number" v-model="idade" />
  </label>

  <!-- Verificando a idade diretamente no template -->
  <p v-if="idade > 18">Maior de idade</p>
  <p v-else>Menor de idade</p>

  <!-- Exibindo o valor da idade -->
  <p>{{ idade }}</p>
</template>
