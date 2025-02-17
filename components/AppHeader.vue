<template>
    <header class="header" :class="{ 'scrolled': isScrolled }">
        <nav class="nav-container">
            <div class="logo">
                <img src="~/assets/images/Logo.svg" alt="Nexcent" />
            </div>

            <div class="nav-links-menu" :class="{ 'active': isMenuOpen }">
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
    height: 70px;
    top: 0;
    width: 100%;
    background-color: var(--Silver);
    transition: all 0.3s ease;
    z-index: 1000;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.header.scrolled {
    background-color: var(--White);
    box-shadow: 0px 4px 8px 0px rgba(171, 190, 209, 0.4);
}

.nav-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 0 105px;
    width: 100%;
}

.logo {
    padding-right: 20px;
    flex-shrink: 0;
}

.nav-links-menu {
    display: flex;
    align-items: center;
    gap: 124.5px;
}

.nav-links {
    display: flex;
    gap: 50px;
}

.auth-btns {
    display: flex;
    gap: 14px;
}

.login-btn {
    background: var(--Silver);
    color: var(--Primary);
    border: none;
    cursor: pointer;
    transition: opacity 0.3s ease;

    font-size: 14px;
    font-weight: 500;
    border-radius: 6px;
    padding: 10px 20px;
    gap: 10px;
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
}

.signup-btn:hover {
    opacity: 0.9;
}

.hamburger {
    display: none;
}

@media (max-width: 1300px) {
    .nav-container {
        margin: auto;
        padding: 0 20px;
    }
    .hamburger {
        display: flex;
        flex-direction: column;
        gap: 5px;
        cursor: pointer;
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


    .nav-links-menu {
        display: none;
        text-align: center;
        transition: 0.3s ease;
    }

    .nav-links-menu.active {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        position: fixed;
        top: 70px;
        left: 0;
        width: 100%;
        padding-bottom: 32px;
        opacity: 1;
        background: var(--Silver);
        box-shadow: 0px 4px 8px 0px rgba(171, 190, 209, 0.4);
        transform: translateY(0);
        gap: 25px;
    }

    .nav-links.active,
    .auth-btns.active {
        display: flex;
        flex-direction: column;
        gap: 25px;
    }
}
</style>