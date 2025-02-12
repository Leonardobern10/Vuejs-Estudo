<script setup>
import Incrementador from "./Incrementador.vue";
import { ref } from "vue";

const contador = ref(0);

function responderAoClique() {
  contador.value++; // Atualiza a ref corretamente
}
</script>

<template>
  <Incrementador @aumentar="responderAoClique" />
  <div class="container">{{ contador }}</div>
</template>

<style scoped>
.container {
  width: 120px;
  height: 120px;
  border: 1px solid black;
}
</style>
