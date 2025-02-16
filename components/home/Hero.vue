<template>
    <section class="hero">
        <div class="container">
            <div class="carousel" @touchstart="startSwipe" @touchmove="moveSwipe" @touchend="endSwipe"
                @mousedown="startMouseSwipe" @mousemove="moveMouseSwipe" @mouseup="endMouseSwipe"
                @mouseleave="endMouseSwipe">
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
            touchStartX: 0,
            touchEndX: 0,
            isMouseDown: false,
            isDragging: false, // to track movement
        };
    },
    methods: {
        goToSlide(index) {
            this.currentIndex = index;
        },

        // **Touch Events**
        startSwipe(event) {
            this.touchStartX = event.touches[0].clientX;
            this.isDragging = false;
        },
        moveSwipe(event) {
            this.isDragging = true;
            this.touchEndX = event.touches[0].clientX;
        },
        endSwipe() {
            if (this.isDragging) {
                this.handleSwipe();
            }
        },

        // **Mouse Events**
        startMouseSwipe(event) {
            this.isMouseDown = true;
            this.isDragging = false; // Reset drag flag
            this.touchStartX = event.clientX;
        },
        moveMouseSwipe(event) {
            if (this.isMouseDown) {
                this.isDragging = true; // Mark as dragging
                this.touchEndX = event.clientX;
            }
        },
        endMouseSwipe() {
            if (this.isMouseDown && this.isDragging) {
                this.handleSwipe();
            }
            this.isMouseDown = false;
        },

        // **Swipe Logic**
        handleSwipe() {
            const swipeDistance = this.touchStartX - this.touchEndX;
            const swipeThreshold = 50; // Minimum distance for a swipe

            if (swipeDistance > swipeThreshold) {
                this.nextSlide();
            } else if (swipeDistance < -swipeThreshold) {
                this.prevSlide();
            }
        },

        nextSlide() {
            if (this.currentIndex < 2) {
                this.currentIndex++;
            } else {
                this.currentIndex = 0; // Loop back to first slide
            }
        },
        prevSlide() {
            if (this.currentIndex > 0) {
                this.currentIndex--;
            } else {
                this.currentIndex = 2; // Loop back to last slide
            }
        },
    },
};
</script>

<style>
.hero {
    width: 100%;
    overflow: hidden;
    align-items: center;
}

.hero .container {
    background-color: var(--Silver);
    display: flex;
    align-items: center;
    justify-content: center;
}

.carousel {
    display: flex;
    align-content: center;
    justify-content: start;
    width: 100%;
    height: 100%;
    /* overflow: clip; */
    position: relative;
    padding: 96px 144px;
    overflow: hidden;
}

.carousel-inner {
    display: flex;
    transition: transform 0.5s ease-in-out;
    width: 300%;
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
    font-size: clamp(40px, 5vw, 64px);
    font-weight: 600;
    line-height: 76px;
    text-align: left;
}

.hero-text h1 {
    font-size: clamp(40px, 5vw, 64px);
    color: var(--D-Grey);
    text-align: left;
}

.hero-text span {
    color: var(--Primary);
}

.hero-text p {
    font-size: clamp(14px, 2vw, 16px);
    font-weight: 400;
    color: var(--Grey);
    padding-top: 16px;
    word-wrap: break-word;
    overflow-wrap: break-word;
    text-align: left;
}

.hero-img {
    flex: 1;
    flex-shrink: 0;
    /* max-width: 50%; */
    /* max-width: 100%; */
    margin: 0 144px;
    /* display: flex;
    justify-content: center;
    align-items: center; */

    min-width: 300px;
    text-align: center;
}

.hero-img img {
    max-width: 100%;
    height: auto;
    max-height: 400px;
}

.carousel-indicators {
    display: flex;
    justify-content: center;
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
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


@media (max-width: 1400px) {

    .carousel-inner .hero-section {
        flex-direction: column-reverse;
        align-items: center;
    }

    .carousel {
        justify-content: center;
        padding: 43px 1%;
    }

    .hero-section {
        gap: 50px;
    }

    .hero-content {
        padding: 0;
        text-align: center;
    }

    .hero-text {
        line-height: normal;
    }

    .hero-text,
    .hero-text h1,
    .hero-text p {
        text-align: center;
    }

    .hero-text p {
        font-size: 14px;
        max-width: 90%;
        margin: 0 auto;
        line-height: 24px;
    }

    .hero-img {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .hero-img img {
        width: 80%;
    }

    .hero-btn {
        justify-content: center;

    }
}
</style>