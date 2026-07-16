<template>
    <TheHeader />
    <main>
        <TheHero />
    </main>
    <TheFooter />
</template>

<script setup lang="ts">
import TheHeader from './components/the-header.vue';
import TheHero from './components/the-hero.vue';
import TheFooter from './components/the-footer.vue';
</script>

<style lang="scss">
@import './assets/styles.scss';
</style>

<style lang="css">
@import 'tailwindcss';
</style>
