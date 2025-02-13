<script setup>
import { ref } from "vue";
import Incrementador from "./components/Incrementador.vue";
const contador = ref(0);
const aumentar = () => {
  contador.value++;
};
</script>

<template>
  <p>{{ contador }}</p>
  <p v-if="contador % 2 == 0">Numero par</p>
  <Incrementador @aumentar="aumentar" />
</template>
