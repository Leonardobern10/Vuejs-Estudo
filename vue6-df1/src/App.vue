<script setup>
import { ref } from 'vue';

const contador = ref(0);

const aumentar = () => {
    contador.value++;
};

const diminuir = () => {
    if (contador.value > 0) {
        contador.value--;
    }
};

const resetar = () => (contador.value = 0);
</script>

<template>
    <h1>{{ contador }}</h1>
    <button @click="aumentar">Aumentar</button>
    <button @click="diminuir">Diminuir</button>
    <button @click="resetar">Resetar</button>
</template>
