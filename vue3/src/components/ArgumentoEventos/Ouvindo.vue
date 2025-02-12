<script setup>
import { ref } from "vue";
import Emitindo from "./Emitindo.vue";

const contador = ref(0);

function incrementar(valor) {
  contador.value += valor;
}
</script>

<template>
  <p>Contador: {{ contador }}</p>
  <Emitindo @incrementar-contador="incrementar" />
</template>
