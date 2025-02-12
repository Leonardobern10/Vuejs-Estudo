<script setup>
import { ref } from "vue";
import ComponentesDInamicos from "./components/ComponentesDInamicos.vue";

const posts = ref([
  { id: 1, title: "My journey with vue" },
  { id: 2, title: "Blogging with vue" },
  { id: 3, title: "Why Vue is so fun" },
]);

const postFontSize = ref(1);
</script>

<template>
  <ComponentesDInamicos />
</template>
