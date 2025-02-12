<script setup>
import { ref } from "vue";

const mensagem = ref("");
const aceito = ref(false);
const escolha = ref("react");
</script>

<template>
  <!--* O texto digitado no input está vinculado à variável mensagem -->
  <div class="ex">
    <input v-model="mensagem" placeholder="Digite Algo" />
    <p>{{ mensagem }}</p>
  </div>

  <div class="ex">
    <input type="checkbox" v-model="aceito" />Aceito os termos
    <p>{{ aceito }}</p>
  </div>
  <div class="ex">
    <input type="radio" v-model="escolha" value="vue" />vue
    <input type="radio" v-model="escolha" value="react" /> react
    <p>Escolha: {{ escolha }}</p>
  </div>
</template>

<style scoped>
.ex {
  width: 100%;
  height: fit-content;
  border: 2px solid black;
  padding: 1rem;
}
</style>
