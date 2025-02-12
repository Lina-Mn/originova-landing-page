<template>
    <div class="home">
        
        <div class="hero-section">
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

        <div class="community">
        </div>
    </div>
</template>

<style>
.home {
    padding-top: 80px;
    height: 100vh;
    background-color: var(--Silver);

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.hero-section {
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
    align-content:first baseline;
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

.community {}
</style>