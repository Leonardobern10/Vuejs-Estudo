<template>
  <div class="alert-box">
    <strong>This is an Error for Demo Purposes</strong>
    <slot />
  </div>
</template>

<style scoped>
.alert-box {
  background-color: rgba(104, 100, 100, 0.303);
  display: flex;
  flex-direction: column;
}
</style>
