<script setup>
import BeNice from './views/BeNice.vue';
</script>

<template>
  <BeNice />
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500&display=swap');
body {
  margin: 0;
  padding: 0;
  display: flex;
  font-family: 'Montserrat', sans-serif;
  font-weight: 500;
  background: hsla(191, 88%, 81%, 1);
  background: linear-gradient(
    90deg,
    hsla(191, 88%, 81%, 1) 0%,
    hsla(260, 72%, 82%, 1) 50%,
    hsla(247, 73%, 69%, 1) 100%
  );
}
</style>
