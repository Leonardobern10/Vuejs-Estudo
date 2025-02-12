<script setup>
import { ref } from "vue";

const msg = ref("Hello World");
</script>

<template>
  <h1>V-text</h1>
  <div v-text="msg"></div>
  <div v-html="html"></div>
</template>
