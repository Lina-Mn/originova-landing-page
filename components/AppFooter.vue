<template>
    <footer class="bg-gray-900 text-white py-12">
        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-4 gap-8">
                <div>
                    <img src="~/public/Logo-white.svg" alt="Nexcent" class="h-8 mb-4" />
                    <p class="text-gray-400">Copyright © 2024 Nexcent ltd.</p>
                    <p class="text-gray-400">All rights reserved</p>
                </div>
                <div v-for="(column, index) in footerColumns" :key="index">
                    <h4 class="font-semibold mb-4">{{ column.title }}</h4>
                    <ul class="space-y-2">
                        <li v-for="(link, linkIndex) in column.links" :key="linkIndex">
                            <a href="#" class="text-gray-400 hover:text-white">
                                {{ link }}
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
const footerColumns = [
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
        links: ['Subscribe to newsletter']
    }
]
</script>