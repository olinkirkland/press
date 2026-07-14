<script setup lang="ts">
import Button from './button.vue';
import HeaderButton from './header-button.vue';
</script>

<template>
    <section class="fixed z-1 w-full flex justify-center">
        <header class="flex justify-between items-center p-3 max-w-page">
            <img class="h-15" src="../assets/images/logo/logo-on-dark.png" />
            <div class="flex gap-5">
                <HeaderButton>Home</HeaderButton>
                <HeaderButton>About</HeaderButton>
                <HeaderButton> Collection </HeaderButton>
                <HeaderButton>Software</HeaderButton>
            </div>
            <div class="flex gap-2 mr-10">
                <Button primary>
                    <img src="../assets/icons/black/link.png" />
                    itch.io
                </Button>
            </div>
        </header>
    </section>
</template>
