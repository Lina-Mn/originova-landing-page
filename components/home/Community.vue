<template>
    <section class="community">
        <div class="container">
            <div class="community-section">
                <h2 class="h2"> Manage your entire community in a single system </h2>
                <p> Who is Nextcent suitable for? </p>
            </div>
            <div class="features-grid">
                <div v-for="(feature, index) in features" :key="index" class="feature-card">
                    <div class="member">
                        <img :src="feature.icon" :alt="feature.title" />
                        <h3>{{ feature.title }}</h3>
                    </div>
                    <p>{{ feature.description }}</p>
                </div>
            </div>
        </div>
    </section>
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

.community .container {
    gap: 16px;
}

.community-section h2 {
    text-align: center;
    margin: 0 449px;
}

.community-section p {
    text-align: center;
    padding-top: 8px;
}

.features-grid {
    display: flex;
    gap: 128px;
    padding: 16px 144px;
}


.feature-card {
    align-content: center;
    box-shadow: 0px 2px 4px 0px rgba(171, 190, 209, 0.2);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    gap: 8px;
}

.feature-card .member {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.feature-card h3 {
    margin-bottom: 0.5rem;
    font-weight: 700;
    font-size: 28px;
    line-height: 36px;
    text-align: center;
    padding: 0 5%;
}

.feature-card img {
    min-height: 65px;
    min-width: 65px;
    margin: auto;
    display: block;
    flex-shrink: 0;
    object-fit: contain;
}

.feature-card p {
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0%;
    text-align: center;
    padding: 0 24px 24px 24px;
}


@media (max-width: 1400px) {
    .community-section h2 {
        margin: 0;
    }
}

@media (max-width: 1100px) {
    .community-section h2 {
        margin: 0;
    }

    .features-grid {
        flex-direction: column;
        gap: 50px;
        padding: 16px 30px;
    }

    .feature-card h3 {
        padding: 0;
    }
}
</style>