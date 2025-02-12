<template>
    <header class="header">
        <nav class="nav-container">
            <div class="logo">
                <img src="~/public/Logo.svg" alt="Nexcent" />
            </div>
            <div class="nav-links">
                <NuxtLink v-for="item in menuItems" :key="item" :to="item.toLowerCase()" class="nav-link">
                    {{ item }}
                </NuxtLink>
            </div>
            <div class="auth-btns">
                <button class="login-btn">Login</button>
                <button class="signup-btn">Sign up</button>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    data() {
        return {
            menuItems: ['Home', 'Service', 'Feature', 'Product', 'Testimonial', 'FAQ'],
        };
    }
}
</script>

<style>
.header {
    position: fixed;
    width: 100%;
    background: var(--White);
    box-shadow: 0px 4px 8px 0px rgba(171, 190, 209, 0.4);
    height: 70px;
    padding: 16px 144px 16px 144px;
    z-index: 1;
}

.nav-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo img {
    height: 34px;
}

.nav-link {
    text-decoration: none;
    margin: 0 1rem;
}

.nav-link:hover {
    color: var(--Primary);
}

.auth-btns {
  display: flex;
  gap: 14px;
}

.login-btn {
    color: var(--Primary);
    background: none;
    border: none;
    cursor: pointer;
}

.signup-btn {
    background-color: var(--Primary);
    color: var(--White);
    border: none;
    border-radius: 6px;
    padding: 10px 20px;
    border-radius: 4px;
    cursor: pointer;
}

</style>