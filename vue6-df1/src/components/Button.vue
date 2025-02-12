<script setup>
defineEmits(['aumentar', 'diminuir', 'resetar']);
</script>
<template>
    <button @click="$emit('aumentar')">Aumentar</button>
    <button @click="$emit('diminuir')">Diminuir</button>
    <button @click="$emit('resetar')">Resetar</button>
</template>
