<template>
    <section class="achievements">
        <div class="container">
            <div class="section-heading">
                <h2 class="h2">
                    Helping a local
                    <br />
                    <span>business reinvent itself</span>
                </h2>
                <p>We reached here with our hard work and dedication</p>
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
    </section>
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
    display: flex;
    justify-content: center;
}

.achievements .container {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    width: 100%;
    padding: 0 20px;
    gap: 72px;
}

.section-heading {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: start;
    margin: 20px 72px 20px 0;
}

.section-heading span {
    color: var(--Primary);
}

.section-heading p {
    color: var(--text-color);
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    padding: 8px 0 0 0;
    max-width: 500px;
}

.counts {
    margin: 64px 0;
}

.stats-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 40px;
    padding: 20px 0;
    margin-left: 72px;
}

.stat-card {
    display: flex;
    align-items: center;
    gap: 30px;
}

.stat-icon {
    width: 48px;
    height: 48px;
    flex-shrink: 0;
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
}

.stat-label {
    color: var(--Grey);
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
}

@media (max-width: 1100px) {
    .achievements .container {
        flex-direction: column;
        gap: 0;
    }

    .section-heading {
        margin: 20px 0 20px 0;
        padding: 20px 0 0 0;
        text-align: center;
    }

    .stats-grid {
        margin: 0;
        padding: 0;
    }

    .counts {
        margin: 0;
    }
}



@media (max-width: 992px) {

    .stats-grid {
        gap: 30px;
    }

    .stat-card {
        gap: 0;
    }

    .stat-value {
        font-size: 24px;
        line-height: 32px;
    }
}

@media (max-width: 768px) {

    .section-heading h2 {
        font-size: 28px;
        line-height: 36px;
    }

    .counts {
        padding: 40px 0;
    }

    .stats-grid {
        gap: 24px;
    }

    .stat-card {
        justify-content: flex-start;
    }
}

@media (max-width: 480px) {
    .section-heading {
        padding: 48px 0 0 0;
    }

    .section-heading h2 {
        font-size: 24px;
        line-height: 32px;
    }

    .section-heading p {
        font-size: 14px;
        line-height: 20px;
    }

    .counts {
        padding: 32px 0;
    }

    .stat-icon {
        width: 40px;
        height: 40px;
    }

    .stat-value {
        font-size: 20px;
        line-height: 28px;
    }

    .stat-label {
        font-size: 14px;
        line-height: 20px;
    }
}
</style>