<template>
  <div class="welcome-container">
    <h1>Welcome to our user and items system!</h1>
    <FlippableCardGrid />
  </div>
</template>

<script setup>
import FlippableCardGrid from "./FlippableCardGrid.vue";
</script>

<style scoped>
.welcome-container {
  text-align: center;
  margin-top: 3rem;
}

h1 {
  margin-bottom: 2rem;
  font-size: 2rem;
  color: white;
}
</style>
