<template>
    <div class="achievements">
        <div class="section-heading">
            <h2 class="h2">
                Helping a local
            <br />
                <span> business reinvent itself </span>
            </h2>
            <p> We reached here with our hard work and dedication </p>
        </div>
        <div class="counts">
            <div class="stats-grid">
                <div class="stat-card" v-for="(stat, index) in stats" :key="index">
                    <img :src="stat.icon" :alt="stat.label" class="stat-icon">
                    <div class="stat-content">
                        <div class="stat-value">{{ stat.value }}</div>
                        <div class="stat-label">{{ stat.label }}</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import clubsIcon from '@/assets/icons/Clubs.svg';
import membersIcon from '@/assets/icons/Members.svg';
import paymentIcon from '@/assets/icons/Payment.svg';
import eventIcon from '@/assets/icons/EventBooking.svg';

export default {
    data() {
        return {
            stats: [
                { value: '2,245,341', label: 'Members', icon: membersIcon },
                { value: '46,328', label: 'Clubs', icon: clubsIcon },
                { value: '828,867', label: 'Event Bookings', icon: eventIcon },
                { value: '1,926,436', label: 'Payments', icon: paymentIcon }
            ],
        }
    },
}
</script>

<style>
.achievements {
    background-color: var(--Silver);
    margin-top: 48px;
    display: flex;
    justify-content: center;
    justify-items: center;
    width: 100dvw;
}

.section-heading {
    padding: 84px 144px;
    display: flex;
    flex-direction: column;  /* stacks items vertically */
    justify-content: center; /* centers items vertically */
}

.section-heading span {
    color: var(--Primary);
}

.section-heading p {
    color: var(--text-color);
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0%;
    padding: 8px 0 0 0;
}

.counts {
    padding: 64px 144px;
}

.stats-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr); /* 2 columns */
    gap: 40px;
    padding: 20px;
}

.stat-card {
    display: flex;
    align-items: center;
    gap: 30px;
}

.stat-icon {
    width: 48px;
    height: 48px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.stat-content {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 6px 0 6px 16px;    
}

.stat-value {
    color: var(--D-Grey);
    font-weight: 700;
    font-size: 28px;
    line-height: 36px;
    letter-spacing: 0%;
}

.stat-label {
    color: var(--Grey);
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0%;
}

</style>