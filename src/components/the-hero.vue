<template>
    <div
        id="hero"
        class="h-128"
        ref="heroRef"
        @mouseenter="onMouseEnter"
        @mouseleave="onMouseLeave"
    >
        <div class="w-full h-full background" :style="backgroundStyle"></div>
    </div>
</template>

<script setup lang="ts">
import { ref, computed, onBeforeUnmount } from 'vue';

const heroRef = ref<HTMLElement | null>(null);

const currentX = ref(0);
const currentY = ref(0);

const targetX = ref(0);
const targetY = ref(0);

let rafId: number | null = null;
const isHovered = ref(false);

const lerp = (start: number, end: number, amt: number) => (1 - amt) * start + amt * end;

function animate() {
    currentX.value = lerp(currentX.value, targetX.value, 0.1);
    currentY.value = lerp(currentY.value, targetY.value, 0.1);

    rafId = requestAnimationFrame(animate);
}

function onMouseEnter() {
    isHovered.value = true;
    window.addEventListener('mousemove', onGlobalMouseMove);

    if (!rafId) {
        animate();
    }
}

function onGlobalMouseMove(e: MouseEvent) {
    if (!heroRef.value) return;

    const rect = heroRef.value.getBoundingClientRect();
    const centerX = rect.left + rect.width / 2;
    const centerY = rect.top + rect.height / 2;

    // Set the target coordinates
    targetX.value = (e.clientX - centerX) / 30;
    targetY.value = (e.clientY - centerY) / 30;
}

function onMouseLeave() {
    isHovered.value = false;
    targetX.value = 0;
    targetY.value = 0;

    window.removeEventListener('mousemove', onGlobalMouseMove);
}

onBeforeUnmount(() => {
    if (rafId) cancelAnimationFrame(rafId);
    window.removeEventListener('mousemove', onGlobalMouseMove);
});

const backgroundStyle = computed(() => ({
    transform: `translate(${-currentX.value}px, ${-currentY.value}px) scale(1.25)`,
}));
</script>

<style lang="scss" scoped>
#hero {
    overflow: hidden;
    position: relative;

    > .background {
        background: url('./hero-image.webp') no-repeat center/cover;
        filter: blur(5px);
        transition: transform 0.1s ease-out;
        transform: scale(1.25);
    }
}
</style>
