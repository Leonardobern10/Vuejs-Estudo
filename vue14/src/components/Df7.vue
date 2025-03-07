<script setup>
import { ref } from "vue";

const imagens = ref([
  { url: "/img/cadeira.jpg", alt: "Cadeira" },
  { url: "/img/mesa.jpg", alt: "Mesa" },
  { url: "/img/lampada.jpg", alt: "Lâmpada" },
]);
</script>

<template>
  <div>
    <img
      v-for="imagem in imagens"
      :key="imagem.url"
      :src="imagem.url"
      :alt="imagem.alt"
    />
  </div>
</template>
