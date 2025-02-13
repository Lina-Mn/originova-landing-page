<template>
    <div class="calendar">
        <div class="pana">
            <img src="~/assets/images/Pana.svg" alt="Mobile LogIng" srcset="">
        </div>
        <div class="calendar-content">
            <div class="calendar-text">
                <h2 class="h2"> How to design your site footer like we did </h2>
                <p> Donec a eros justo. Fusce egestas tristique ultrices. Nam tempor, augue nec tincidunt molestie, massa nunc varius arcu, at scelerisque elit erat a magna. Donec quis erat at libero ultrices mollis. In hac habitasse platea dictumst. Vivamus vehicula leo dui, at porta nisi facilisis finibus. In euismod augue vitae nisi ultricies, non aliquet urna tincidunt. Integer in nisi eget nulla commodo faucibus efficitur quis massa. Praesent felis est, finibus et nisi ac, hendrerit venenatis libero. Donec consectetur faucibus ipsum id gravida. </p>
            </div>
            <div class="calendar-btn">
                <button> Learn More </button>
            </div>
        </div>
    </div>
</template>

<style>
.calendar {
    display: flex;
    align-items: center;
    margin-top: 48px;
    gap: 50px;
    width: 100dvw;
}

.pana {
    margin-left: 144px;
    height: 100%;
    width: 100%;
}

.pana img {
    height: 100%;
    width: 100%;
}

.calendar-content {
    margin: 63px 144px;
    display: flex;
    flex-direction: column;
}

.calendar-text {
    margin-left: 60px;
    padding-right: 60px;
}

.calendar-text p {
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0%;
    color: var(--Grey);
    margin-top: 16px;
}

.calendar-btn {
    margin: 32px 0 0 60px;
}

.calendar-btn button {
    padding: 14px 32px;
    background-color: var(--Primary);
    width: 151px;
    height: 52px;
    gap: 10px;
    padding: 14px 32px;
    color: var(--White);
    border-radius: 4px;

    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0%;
    text-align: center;
}

</style>