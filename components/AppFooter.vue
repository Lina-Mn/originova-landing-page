<template>
    <div class="footer-grid">
        <div class="footer-brand">
            <h1 class="h1"> Pellentesque suscipit fringilla libero eu. </h1>
            <button class="btn-primary-icon"> Get a Demo -> </button>
        </div>
        <div class="footer-info">
            <div class="company-info">
                <img src="~/assets/images/Logo-white.svg" alt="Nexcent">
                <div class="copyrights">
                    <p>Copyright © 2024 Nexcent ltd.</p>
                    <p>All rights reserved</p>
                </div>
                <div class="social-links">
                    <div class="social-link" v-for="(slink, sIndex) in socialLinks" :key="sIndex">
                        <img :src="slink.icon" :alt="slink.label" />
                    </div>
                </div>
            </div>
            <div class="footer-links">
                <div class="footer-link" v-for="(column, index) in columns" :key="index">
                    <h4 class="h4">{{ column.title }}</h4>
                    <ul>
                        <li v-for="(link, linkIndex) in column.links" :key="linkIndex">
                            <a href="#">{{ link }}</a>
                        </li>
                    </ul>
                    <div v-if="column.newsletter" class="newsletter-container">
                        <div class="input-container">
                            <input type="email" placeholder="Enter your email">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import InstagramIcon from '@/assets/icons/Instagram.svg'
import DribbbleIcon from '@/assets/icons/Dribbble.svg'
import TwitterIcon from '@/assets/icons/Twitter.svg'
import YoutubeIcon from '@/assets/icons/Youtube.svg'

export default {
    data() {
        return {
            socialLinks: [
                {
                    label: 'Instagram',
                    icon: InstagramIcon
                },
                {
                    label: 'Dribbble',
                    icon: DribbbleIcon
                },
                {
                    label: 'Twitter',
                    icon: TwitterIcon
                },
                {
                    label: 'Youtube',
                    icon: YoutubeIcon
                },
            ],
            columns: [
                {
                    title: 'Company',
                    links: ['About us', 'Blog', 'Contact us', 'Pricing', 'Testimonials']
                },
                {
                    title: 'Support',
                    links: ['Help center', 'Terms of service', 'Legal', 'Privacy policy', 'Status']
                },
                {
                    title: 'Stay up to date',
                    newsletter: true,
                }
            ]
        }
    }
}
</script>

<style>
.footer-grid {
    margin-top: 54px;
    background-color: var(--Silver);
    color: var(--Silver);
    gap: 125px;
}

.footer-brand {
    padding: 32px 276.5px 0 275.6px;
    text-align: center;
}

.footer-brand button {
    margin: 32px 0 32px 0;
}

.social-links {
    display: flex;
    gap: 16px;
}

/* 2nd part of footer */
.footer-info {
    background-color: var(--Black);
    display: flex;
    gap: 125px;
}

.company-info {
    display: flex;
    flex-direction: column;
    align-content: center;
    justify-content: space-between;
    padding: 64px 0 75px 165px;
}

.footer-links {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    margin: 64px 165px 64px auto;
    gap: 30px;
}

.footer-link h4 {
    color: var(--White);
    text-align: left;
}

.footer-link ul {
    margin-top: 24px;
}

.footer-link ul li {
    margin-bottom: 12px;
}

.input-container {
    position: relative;
    display: inline-block;
}

.input-container input {
    background-color: #515b60;
    border-radius: 8px;
    opacity: 20%;
    
    padding: 9px 30px 11px 12px;
}

input::placeholder,
textarea::placeholder {
    color: var(--White);
    font-weight: 400;
    font-size: 14px;
    letter-spacing: 0%;
}

.input-container::after {
    content: "";
    background-image: url('~/assets/icons/send.svg');
    background-size: contain;
    background-repeat: no-repeat;
    width: 16.5px;
    height: 16.5px;
    position: absolute;
    right: 10px;
    top: 50%;
    transform: translateY(-50%);
}
</style>