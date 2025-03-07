<script setup>
import { ref } from "vue";

const frutas = ref(["Maçã", "Banana", "Laranja"]);
</script>

<template>
  <ul>
    <li v-for="(fruta, index) in frutas" :key="index">
      {{ index + 1 }} - {{ fruta }}
    </li>
  </ul>
</template>
