<script setup>
import { ref } from "vue";

const items = ref([{ message: "Pow" }, { message: "Tei" }]);
</script>

<template>
  <li v-for="{ message } in items">
    {{ message }}
  </li>
</template>
