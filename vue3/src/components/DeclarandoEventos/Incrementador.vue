<script setup>
const emit = defineEmits(["aumentar"]); // Declaração do evento

function dispararEvento() {
  emit("aumentar"); // Emissão do evento
}
</script>

<template>
  <button @click="dispararEvento">Clicou</button>
</template>
