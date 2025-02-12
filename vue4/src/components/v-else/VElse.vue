<script setup>
const value = Math.random();
</script>

<template>
  <h1>V-else</h1>
  <p>{{ value }}</p>
  <div v-if="value > 0.5">Agora você me vê</div>
  <div v-else>Agora você não me vê</div>
</template>
