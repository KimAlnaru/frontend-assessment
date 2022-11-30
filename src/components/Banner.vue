<script setup>

defineProps({
    title: {
        type: String,
        required: true,
    },
    subtitle: {
        type: String,
        required: true,
    }
})

</script>

<template>
    <div class="position-relative d-flex flex-column">
        <img src="@/assets/images/1920x650.png" alt="" class="desktop-banner w-100 fade-in-down" />
        <img src="@/assets/images/600x600.png" alt="" class="mobile-banner w-100" />
        <div class="banner movearea">
            <h2 class="banner__title">{{ title }}</h2>
            <p class="banner__subtitle">{{ subtitle }}</p>
        </div>
    </div>  
</template>

<style scoped>
    .desktop-banner {
        display: none !important;
    }
    .mobile-banner {
        display: flex !important;
    }

    @media (min-width: 601px) {
        .desktop-banner {
            display: flex !important;
        }
        .mobile-banner {
            display: none !important;
        }
    }

    .banner {
        position: absolute;
        width: 100%;
        background: rgba(0, 0, 0, 0.3);
        height: -webkit-fill-available;
        text-align: center;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
    .banner__title {
        font-weight: bold;
        font-size: 2.9rem;
        color: #ffffff;        
    }

    p.banner__subtitle {
        font-size: 1.3rem;
        color: #ffffff;      
    }

</style>
