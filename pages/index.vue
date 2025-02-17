<script>
import { 
    BodySectionAchievements, 
    BodySectionCalendar, 
    BodySectionUnlock, 
    BodySectionUpdates, 
    HomeCommunity, 
    HomeHero 
} from '#components';

</script>

<template>
    <div class="landing-page">
        <!-- Home Section -->
        <div class="home-section">
            <HomeHero />
            <HomeCommunity />
        </div>
        <div class="body-section">
            <!-- Body Section -->
            <BodySectionUnlock />
            <BodySectionAchievements />
            <BodySectionCalendar />
            <BodySectionUpdates />
        </div>
    </div>
</template>

<style>
.landing-page {
    display: flex;
    flex-direction: column;
    gap: 40px;
    top: calc(100vh - 70px);
    margin-top: 30px;
}

.home-section,
.body-section {
    display: flex;
    flex-direction: column;
    gap: 48px;
}
</style>