<template>
    <section class="hero">
        <div class="container">
            <div class="carousel">
                <div class="carousel-inner" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
                    <div v-for="n in 3" :key="n" class="hero-section">
                        <div class="hero-content">
                            <div class="hero-text">
                                <h1 class="h1"> Lessons and insights </h1>
                                <span> from 8 years </span>
                                <p> Where to grow your business as a photographer: site or social media? </p>
                            </div>
                            <div class="hero-btn">
                                <button class="btn-primary-medium"> Register </button>
                            </div>
                        </div>
                        <div class="hero-img">
                            <img src="~/assets/images/Illustration.svg" alt="Hero">
                        </div>
                    </div>
                </div>

                <div class="carousel-indicators">
                    <span v-for="n in 3" :key="n" :class="{ active: currentIndex === n - 1 }"
                        @click="goToSlide(n - 1)"></span>
                </div>
            </div>
        </div>
    </section>
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
.hero {
    width: 100%;
}

.carousel {
    display: flex;
    align-content: center;
    width: 100dvw;
    height: 100%;
    overflow: hidden;
    position: relative;
    padding: 96px 144px;
    background-color: var(--Silver);
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
    justify-content: center;
    padding-left: 104px;
    gap: 32px;
}

.hero-text {
    font-size: 64px;
    font-weight: 600;
    line-height: 76px;
    text-align: left;
}

.hero-text h1 {
    color: var(--D-Grey);
    text-align: left;
}

.hero-text span {
    color: var(--Primary);
}

.hero-text p {
    font-size: 16px;
    font-weight: 400;
    color: var(--Grey);
}

.hero-img {
    flex-shrink: 0;
    max-width: 50%;
    /* max-width: 100%; */
    margin: 0 144px;
}

.hero-img img {
    width: 100%;
    height: auto;
    object-fit: contain;
}

.carousel-indicators {
    display: flex;
    justify-content: center;
    position: absolute;
    bottom: 10px;
    left: 50%;
    gap: 8px;
    margin-bottom: 16px;
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

@media (max-width: 1100px) {
    .carousel-inner
    .hero-section {
        flex-direction: column-reverse;
    }

    .hero-section {
        gap: 50px;
    }

    .hero-img img{
        width: 80%;
    }

    .hero-btn {
        justify-content: center;
    }
}
</style>