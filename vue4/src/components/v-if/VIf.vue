<script setup>
const value = Math.random();
</script>

<template>
  <h1>V-if</h1>
  <div v-if="value > 0.7">{{ value }}</div>
</template>
