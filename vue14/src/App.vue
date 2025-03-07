<script setup>
import Df1 from "./components/Df1.vue";
import Df2 from "./components/Df2.vue";
import Df3 from "./components/Df3.vue";
import Df4 from "./components/Df4.vue";
import Df5 from "./components/Df5.vue";
import Df6 from "./components/Df6.vue";
import Df7 from "./components/Df7.vue";
</script>

<template>
  <div class="container" id="def1">
    <Df1 />
  </div>
  <div class="container">
    <Df2 />
  </div>
  <div class="container">
    <Df3 />
  </div>
  <div class="container">
    <Df4 />
  </div>
  <div class="container">
    <Df5 />
  </div>
  <div class="container">
    <Df6 />
  </div>
  <div class="container">
    <Df7
     />
  </div>
</template>

<style scoped>
.container {
  background-color: antiquewhite;
  border: 2px solid black;
  width: 100%;
  height: 10rem;
  padding: 15px;
}
</style>
