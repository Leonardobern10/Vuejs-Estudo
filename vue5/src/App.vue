<script setup>
import { ref } from "vue";
import Contador from "./components/Contador.vue";

const contador = ref(0);

const aumentar = () => {
  contador.value += 1;
};
</script>
<template>
  <p v-text="contador"></p>
  <input type="text" onchange="contador.value" />
  <Contador @aumentar="aumentar" />
</template>
