<script>
import Community from '~/components/Community.vue';
import Hero from '~/components/Hero.vue';


</script>

<template>
<div class="home">
    <Hero />
    <Community />
</div>
</template>

<style>
.home {
    height: 100vh;
    background-color: var(--Silver);

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    padding: 0 144px;
    gap: 40px;
}
</style>