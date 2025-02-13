<script setup lang="ts">
import AppHeader from './components/AppHeader.vue';

</script>

<template>
  <div>
    <AppHeader />
    <main class="content">
      <NuxtPage />      
      <!-- <NuxtRouteAnnouncer />
      <NuxtWelcome /> -->
    </main>
    <!-- <AppFooter /> -->
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Inter", serif;
  color: var(--Black);
}

.content {
  margin-top: 70px;
}

</style>