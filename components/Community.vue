<template>
    <div class="community">
        <div class="community-section">
            <h2 class="h2"> Manage your entire community in a single system </h2>
            <p> Who is Nextcent suitable for? </p>
        </div>
        <div class="features-grid">
            <div v-for="(feature, index) in features" :key="index" class="feature-card">
                <img :src="feature.icon" :alt="feature.title" />
                <h3>{{ feature.title }}</h3>
                <p>{{ feature.description }}</p>
            </div>
        </div>
    </div>
</template>

<script>
import membershipIcon from '@/assets/icons/Membership.svg';
import nationalIcon from '@/assets/icons/National.svg';
import clubsIcon from '@/assets/icons/Clubs&Groups.svg';

export default {
    data() {
        return {
            features: [
                {
                    title: 'Membership Organisations',
                    description: 'Our membership management software provides full automation of membership renewals and payments',
                    icon: membershipIcon,
                },
                {
                    title: 'National Associations',
                    description: 'Our membership management software provides full automation of membership renewals and payments',
                    icon: nationalIcon,
                },
                {
                    title: 'Clubs And Groups',
                    description: 'Our membership management software provides full automation of membership renewals and payments',
                    icon: clubsIcon,
                },
            ]

        }
    },
}
</script>

<style>
.community {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 40px;
}

.community-section p {
    text-align: center;
}

.features-grid {
    display: flex;
    gap: 8px;
    padding: 0 144px;
    
}

.feature-card {
    align-content: center;
    margin: 24px 65px;
    box-shadow: 0px 2px 4px 0px rgba(171, 190, 209, 0.2);
}

.feature-card h3 {
    margin-bottom: 0.5rem;
    font-weight: 700;
    font-size: 28px;
    line-height: 36px;
    text-align: center;
    padding: 0 16px;
}

.feature-card img {
    height: 64px;
    margin: auto;
    display: block;
    padding: 0 101px;
}

.feature-card p {
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0%;
    text-align: center;
    padding-bottom: 24px;
}
</style>