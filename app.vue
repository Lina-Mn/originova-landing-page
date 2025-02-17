<script setup lang="ts">
import AppFooter from './components/AppFooter.vue';
import AppHeader from './components/AppHeader.vue';

</script>

<template>
    <AppHeader />
    <main>
      <NuxtPage />
    </main>
    <AppFooter />
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: var(--Black);
  font-family: Inter, serif;
}

body {
  width: 100%;
  overflow-x: hidden;
  background-color: var(--White);
}

</style>