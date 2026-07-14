<template>
    <TheHeader />
    <main>
        <TheHero />
    </main>
</template>

<script setup lang="ts">
import TheHeader from './components/the-header.vue';
import TheHero from './components/the-hero.vue';
</script>

<style lang="scss">
@import './assets/styles.scss';
</style>

<style lang="css">
@import 'tailwindcss';
</style>
