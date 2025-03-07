<script setup>
import { ref } from "vue";
import CMPAux6 from "./CMPAux6.vue";

const produtos = ref([
  { nome: "Cadeira", preco: 100 },
  { nome: "Mesa", preco: 200 },
  { nome: "Lâmpada", preco: 50 },
]);
</script>

<template>
  <div>
    <CMPAux6
      v-for="produto in produtos"
      :key="produto.nome"
      :produto="produto"
    />
  </div>
</template>
