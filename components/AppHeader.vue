<template>
    <header class="header" :class="{ 'scrolled': isScrolled }">
        <nav class="nav-container">
            <div class="logo">
                <img src="~/assets/images/Logo.svg" alt="Nexcent" />
            </div>

            <div class="nav-links" :class="{ 'active': isMenuOpen }">
                <NuxtLink v-for="item in menuItems" :key="item" :to="item.toLowerCase()" class="nav-link"
                    @click="closeMenu">
                    {{ item }}
                </NuxtLink>
            </div>

            <div class="auth-btns" :class="{ 'active': isMenuOpen }">
                <button class="login-btn">Login</button>
                <button class="signup-btn">Sign up</button>
            </div>

            <!-- Hamburger Menu -->
            <div class="hamburger" @click="toggleMenu" :class="{ 'active': isMenuOpen }">
                <div class="bar"></div>
                <div class="bar"></div>
                <div class="bar"></div>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    data() {
        return {
            menuItems: ['Home', 'Service', 'Feature', 'Product', 'Testimonial', 'FAQ'],
            isMenuOpen: false, // Tracks menu state
            isScrolled: false
        };
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
    },
    beforeDestroy() {
        window.removeEventListener('scroll', this.handleScroll);
    },
    methods: {
        toggleMenu() {
            this.isMenuOpen = !this.isMenuOpen;
            // Prevent scrolling when menu is open
            document.body.style.overflow = this.isMenuOpen ? 'hidden' : '';
        },
        closeMenu() {
            this.isMenuOpen = false;
            document.body.style.overflow = '';
        },
        handleScroll() {
            this.isScrolled = window.scrollY > 50;
        },
    }
}
</script>

<style>
.header {
    position: fixed;
    display: flex;
    justify-content: center;
    align-items: center;
    top: 0;
    left: 0;
    width: 100%;
    height: 70px;
    background-color: var(--Silver);
    z-index: 1000;
    transition: all 0.3s ease;
}

.header.scrolled {
    background-color: var(--White);
    box-shadow: 0px 4px 8px 0px rgba(171, 190, 209, 0.4);
}

.nav-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    max-width: 1440px;
    margin: auto;
    padding: 0 24px;
}

/* Added responsive padding */
@media (min-width: 1200px) {
    .nav-container {
        padding: 0 144px;
    }
}

@media (min-width: 768px) and (max-width: 1199px) {
    .nav-container {
        padding: 0 80px;
    }
}

.logo {
    flex: 0 0 auto;
}

.logo img {
    min-width: 155px;
    height: auto;
}

/* Desktop Navigation */
.nav-links {
    display: flex;
    align-items: center;
    flex: 1 1 auto;
    justify-content: center;
    gap: 50px;
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
}

/* Responsive gap adjustments */
@media (min-width: 1100px) and (max-width: 1300px) {
    .nav-links {
        gap: 30px;
    }
}

.nav-link {
    text-decoration: none;
    transition: color 0.3s ease;
}

.nav-link:hover {
    color: var(--Primary);
}

.auth-btns {
    display: flex;
    gap: 14px;
    flex: 0 0 auto;
}

.login-btn {
    background: none;
    color: var(--Primary);
    border: none;
    cursor: pointer;
    padding: 10px 20px;
    font-weight: 500;
    font-size: 14px;
    line-height: 20px;
    transition: opacity 0.3s ease;
}

.login-btn:hover {
    opacity: 0.8;
}

.signup-btn {
    background-color: var(--Primary);
    color: var(--White);
    border: none;
    border-radius: 6px;
    padding: 10px 20px;
    cursor: pointer;
    font-weight: 500;
    font-size: 14px;
    line-height: 20px;
    transition: opacity 0.3s ease;
}

.signup-btn:hover {
    opacity: 0.9;
}

/* Hamburger Menu */
.hamburger {
    display: none;
    flex-direction: column;
    cursor: pointer;
    gap: 5px;
}

.hamburger .bar {
    width: 30px;
    height: 3px;
    background: var(--Primary);
    transition: 0.3s ease;
}

.hamburger.active .bar:nth-child(1) {
    transform: rotate(45deg) translate(6px, 6px);
}

.hamburger.active .bar:nth-child(2) {
    opacity: 0;
}

.hamburger.active .bar:nth-child(3) {
    transform: rotate(-45deg) translate(6px, -6px);
}

/* Medium screens - adjust spacing */
@media (min-width: 1100px) and (max-width: 1440px) {

    .login-btn,
    .signup-btn {
        padding: 10px 15px;
    }

    .auth-btns {
        gap: 10px;
    }
}

@media (max-width: 1100px) {

    .nav-links,
    .auth-btns {
        display: none;
        flex-direction: column;
        position: fixed;
        top: 70px;
        left: 0;
        width: 100%;
        height: calc(100vh - 70px);
        background: var(--Silver);
        text-align: center;
        padding: 40px 0;
        gap: 30px;
        transform: translateY(-100%);
        opacity: 0;
        transition: all 0.3s ease;
    }

    .nav-links.active,
    .auth-btns.active {
        display: flex;
        transform: translateY(0);
        opacity: 1;
    }

    .auth-btns.active {
        top: auto;
        bottom: 100px;
        height: auto;
    }

    .hamburger {
        display: flex;
    }
}

/* Tablet adjustments */
@media (max-width: 768px) {
    .nav-container {
        padding: 0 16px;
    }

    .logo img {
        width: 120px;
        min-width: 120px;
    }
}
</style>