<script setup lang="ts">
import AppFooter from './components/AppFooter.vue';
import AppHeader from './components/AppHeader.vue';

</script>

<template>
  <div class="app-wrapper">
    <AppHeader />
    <main class="content">
      <NuxtPage />
    </main>
    <AppFooter />
  </div>
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
  width: 100dvw;
  overflow-x: hidden;
  background-color: var(--White);
}

.app-wrapper {
  width: 100%;
  min-height: 100vh;
  position: relative;
}

.content {
  margin-top: 70px;
  width: 100%;
  max-width: 100vw;
  overflow-x: hidden;
}
</style>