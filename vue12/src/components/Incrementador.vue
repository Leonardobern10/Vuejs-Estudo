<script setup>
defineEmits(["aumentar"]);
</script>
<template>
  <button @click="$emit('aumentar')">Aumentar</button>
</template>
