<template>
    <header class="header">


        <transition name="menu">
            <div v-if="openMenu" class="right-nav">
                <div class="right-nav__list">
                    <div @click="openMenu = false" class="right-nav__item">
                        <NuxtLink to="#kursHaqida">Kurs haqida</NuxtLink>
                    </div>
                    <div @click="openMenu = false" class="right-nav__item">
                        <NuxtLink to="#kursdaNima">Kursda nimalarni o’rganasiz?</NuxtLink>
                    </div>
                    <div @click="openMenu = false" class="right-nav__item">
                        <NuxtLink to="#faq">FAQ</NuxtLink>
                    </div>
                </div>
                <site-btn title="Kursga yozilish"></site-btn>
                <button @click="openMenu = false" class="x-btn">
                    <img src="~/assets/img/svg/x.svg" alt="x" width="30" height="30">
                </button>
            </div>
        </transition>

        <div class="container">
            <NuxtLink class="logo" to="/">
                <img src="~/assets/img/svg/logo.svg" alt="logo" width="68" height="49">
            </NuxtLink>
            <nav class="nav">
                <div class="item">
                    <NuxtLink to="#kursHaqida">Kurs haqida</NuxtLink>
                </div>
                <div class="item">
                    <NuxtLink to="#kursdaNima">Kursda nimalarni o’rganasiz?</NuxtLink>
                </div>
                <div class="item">
                    <NuxtLink to="#faq">FAQ</NuxtLink>
                </div>
            </nav>
            <div class="link">
                <a class="num" href="#">+998 97 628 28 82</a>
                <site-btn title="Kursga yozilish"></site-btn>
            </div>
            <button @click="openMenu = true" class="bars">
                <svg width="25" height="25" viewBox="0 0 26 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <rect width="26" height="2" rx="1" fill="white" />
                    <rect y="8" width="26" height="2" rx="1" fill="white" />
                    <rect y="16" width="26" height="2" rx="1" fill="white" />
                </svg>
            </button>
        </div>
    </header>
</template>

<script setup>
const openMenu = ref(false)

onMounted(() => {
    const navbarHeight = document.querySelector(".header").clientHeight
    const navbar = document.querySelector(".header");
    window.addEventListener("scroll", (event) => {
        if (window.scrollY > navbarHeight) {
            navbar.classList.add("sticky")
        } else {
            navbar.classList.remove("sticky")
        }
    })
})
</script>

<style>
.menu-enter-active,
.menu-leave-active {
    transition: all 0.5s ease;
    transform: translateX(0);
}

.menu-enter-from,
.menu-leave-to {
    transform: translateX(100%);
    opacity: 0;
}
</style>

