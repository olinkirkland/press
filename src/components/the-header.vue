<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue';
import Button from './button.vue';
import HeaderButton from './header-button.vue';

const isScrolled = ref(false);

const handleScroll = () => {
    isScrolled.value = window.scrollY > 5;
};

onMounted(() => {
    window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
    <section class="fixed z-1 w-full flex justify-center" :class="{ scrolled: isScrolled }">
        <header class="flex justify-between items-center max-w-page">
            <img class="h-15 pt-2" src="../assets/images/logo/logo-on-dark.png" />
            <div class="flex gap-5">
                <HeaderButton>Home</HeaderButton>
                <HeaderButton>About</HeaderButton>
                <HeaderButton> Collection </HeaderButton>
                <HeaderButton>Software</HeaderButton>
            </div>
            <div class="flex gap-2 mr-10">
                <a href="https://itch.io" class="text-white">
                    <img src="../assets/icons/white/link.png" />
                    itch.io
                </a>
            </div>
        </header>
    </section>
</template>

<style lang="scss" scoped>
section {
    background-color: transparent;
    transition: background-color 0.2s;
}

.scrolled {
    background-color: rgba(0, 0, 0, 0.25);
    backdrop-filter: blur(5px);
}
</style>
