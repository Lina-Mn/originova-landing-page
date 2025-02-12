<script setup lang="ts">
import AppFooter from './components/AppFooter.vue';
import AppHeader from './components/AppHeader.vue';
import Home from './components/Home.vue';

</script>

<template>
  <div>
    <AppHeader />
    <Home />
    <!-- <NuxtRouteAnnouncer />
    <NuxtWelcome /> -->
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

:root {
  --Black: #263238;
  --D-Grey: #4D4D4D;
  --Grey: #717171;
  --L_Grey: #89939E;
  --Grey-blue: #ABBED1;
  --Silver: #F5F7FA;
  --White: #FFFFFF;
  --Primary: #4CAF4F;
  --Secondary: #263238;
  --Info: #2194f3;
  --Shade-1: #43A046;
  --Shade-2: #388E3B;
  --Shade-3: #237D31;
  --Shade-4: #1B5E1F;
  --Shade-5: #103E13;
  --Tint-1: #89939E;

  
  --text-color: #333333;
}
</style>