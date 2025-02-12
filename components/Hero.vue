<template>
    <div class="carousel">
        <div class="carousel-inner" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
            <div v-for="n in 3" :key="n" class="hero-section">
                <div class="hero-content">
                    <div class="hero-text">
                        <h1> Lessons and insights </h1>
                        <span> from 8 years </span>
                        <p> Where to grow your business as a photographer: site or social media? </p>
                    </div>
                    <div class="hero-btn">
                        <button> Register </button>
                    </div>
                </div>
                <div class="hero-img">
                    <img src="~/public/Illustration.svg" alt="Hero">
                </div>
            </div>
        </div>

        <div class="carousel-indicators">
            <span v-for="n in 3" :key="n" :class="{ active: currentIndex === n - 1 }" @click="goToSlide(n - 1)"></span>
        </div>
    </div>

</template>

<script>
export default {
    data() {
        return {
            currentIndex: 0,
        };
    },
    methods: {
        goToSlide(index) {
            this.currentIndex = index;
        }
    },
}
</script>

<style>
.carousel {
    display: flex;
    width: 100%;
    overflow: hidden;
    position: relative;

    padding: 96px 144px;

}

.carousel-inner {
    display: flex;
    transition: transform 0.5s ease-in-out;
}

.hero-section {
    flex: 0 0 100%;
    /* show 100% of each slide */
    display: flex;
}

.hero-content {
    display: flex;
    flex-direction: column;
    padding-left: 104px;
}

.hero-text {
    flex: 2;
    font-size: 64px;
    font-weight: 600;
    line-height: 76px;
}

.hero-text h1 {
    color: var(--D-Grey);
}

.hero-text span {
    color: var(--Primary);
}

.hero-text p {
    font-size: 16px;
    font-weight: 400;
    color: var(--Grey);
}

.hero-btn {
    flex: 1;
    align-content: first baseline;
}

.hero-btn button {
    background: var(--Primary);
    color: var(--White);
    font-weight: 500;
    font-size: 16px;
    border-radius: 4px;
    padding: 14px 32px;
}

.hero-img {
    max-width: 100%;
    padding: 0 144px;
}

.carousel-indicators {
    display: flex;
    justify-content: center;
    position: absolute;
    bottom: 10px;
    left: 50%;
    gap: 8px;
}

.carousel-indicators span {
    display: block;
    width: 10px;
    height: 10px;
    margin: 0 5px;
    border-radius: 50%;
    background-color: var(--Tint-2);
    cursor: pointer;
}

.carousel-indicators span.active {
    background-color: var(--Primary);
}
</style>