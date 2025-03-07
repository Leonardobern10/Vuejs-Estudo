<script setup>
import { ref } from "vue";

const objetos = ref([
  { nome: "Cadeira", status: "Ativo" },
  { nome: "Mesa", status: "Inativo" },
  { nome: "Lápis", status: "Ativo" },
]);

const currentStatus = ref("Ativo");
</script>

<template>
  <label for="alterStatus">
    <select v-model="currentStatus" name="alterStatus" id="alterStatus">
      <option value="Ativo">Ativo</option>
      <option value="Inativo">Inativo</option>
    </select>
  </label>
  <ul>
    <li
      v-for="(item, index) in objetos"
      :key="index"
      v-show="item.status === currentStatus"
    >
      {{ item.nome }}
    </li>
  </ul>
  <p>{{ currentStatus }}</p>
</template>
