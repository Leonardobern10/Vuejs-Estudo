<script setup>
import { ref } from "vue";

const contador = ref(0);
</script>

<template>
  <button @click="contador++">Clicou {{ contador }} vezes</button>
</template>
