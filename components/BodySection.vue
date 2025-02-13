<template>
    <div class="container">
        <Unlock />
        <Achievements />
        <Calendar />
        <Updates />
        
    </div>
</template>

<script>
import Unlock from './Unlock.vue';
import Achievements from './Achievements.vue'
import Calendar from './Calendar.vue'
import Updates from './Updates.vue';

export default {
    components: {
        Unlock,
        Achievements,
        Calendar,
        Updates,
    },
}
</script>

<style>
.container {
    width: 100%;
    /* display: flex; */
    /* margin-top: 40px; */
    gap: 48px;
}

</style>