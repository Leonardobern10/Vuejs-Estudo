<script setup>
import VElse from "./components/v-else/VElse.vue";
import VIf from "./components/v-if/VIf.vue";
import VText from "./components/v-text/VText.vue";
</script>

<template>
  <div class="container">
    <VText />
  </div>
  <div class="container">
    <VElse />
  </div>
  <div class="container">
    <VIf />
  </div>
  <div class="container"></div>
</template>

<style scoped>
.container {
  width: 100%;
  height: fit-content;
  padding: 2rem;
  border: 2px solid black;
}
</style>
