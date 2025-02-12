<script setup>
defineEmits(["aumentar"]);
</script>

<template>
  <button type="submit" @click="$emit('aumentar')">Aumentar</button>
</template>
