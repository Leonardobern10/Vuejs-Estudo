<script setup>
import Ouvindo from "./components/ArgumentoEventos/Ouvindo.vue";
import Ouvindo2 from "./components/OuvindoEventos/Ouvindo2.vue";
import Receptor from "./components/DeclarandoEventos/Receptor.vue";
</script>
<template>
  <div class="container">
    <Ouvindo />
  </div>
  <div class="container">
    <Ouvindo2 />
  </div>
  <div class="container">
    <Receptor />
  </div>
</template>
<style scoped>
.container {
  width: 100%;
  height: 250px;
  border: 10px solid blue;
}
</style>
