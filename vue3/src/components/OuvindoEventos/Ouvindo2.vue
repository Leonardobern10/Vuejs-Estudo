<script setup>
import { ref } from "vue";
import Emitindo2 from "./Emitindo2.vue";

const contador = ref(0);

function responserAoClique(n) {
  contador.value += n;
}
</script>

<template>
  <Emitindo2 @aumentar.once="responserAoClique(5)" />
  <div class="container">{{ contador }}</div>
</template>

<style scoped>
.container {
  width: 120px;
  height: 120px;
  border: 1px solid black;
}
</style>
