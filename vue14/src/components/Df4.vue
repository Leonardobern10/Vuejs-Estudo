<script setup>
import { ref } from "vue";

const produtos = ref([
  { nome: "Cadeira", preco: 100 },
  { nome: "Mesa", preco: 200 },
  { nome: "Lâmpada", preco: 50 },
]);
</script>

<template>
  <ul>
    <li v-for="produto in produtos" :key="produto.nome">
      {{ produto.nome }} - R$ {{ produto.preco }}
    </li>
  </ul>
</template>
