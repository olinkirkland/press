<template>
    <div id="hero" ref="heroRef" class="relative w-full h-150">
        <div class="w-full h-full background" :style="backgroundStyle"></div>
        <div id="content" class="absolute w-full h-full top-0">
            <div class="max-w-page p-3 h-full pt-20 mx-auto">
                <div class="h-full grid grid-cols-2">
                    <div class="h-full flex flex-col justify-center gap-5">
                        <h3>
                            Lorem ipsum dolor, sit amet <theme>consectetur</theme> elit. At, soluta.
                        </h3>
                        <p>
                            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Temporibus
                            repudiandae quae molestias nemo asperiores laudantium minima tempora.
                            Laboriosam nobis saepe et quas asperiores, veniam dolorum neque? Qui
                            soluta tenetur esse.
                        </p>
                        <Button>Download Now</Button>
                    </div>
                    <div>
                        <div class="flex gap-1">
                            <button>
                                <img
                                    disabled
                                    class="w-10 rotate-180"
                                    src="../assets/icons/white/arrow-circle.png"
                                />
                            </button>
                            <button>
                                <img class="w-10" src="../assets/icons/white/arrow-circle.png" />
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import { computed, onBeforeUnmount, onMounted, ref } from 'vue';
import Theme from './theme.vue';
import Button from './button.vue';

const heroRef = ref<HTMLElement | null>(null);

const currentX = ref(0);
const currentY = ref(0);

const targetX = ref(0);
const targetY = ref(0);

let rafId: number | null = null;
const isHovered = ref(false);

const lerp = (start: number, end: number, amt: number) => (1 - amt) * start + amt * end;

function animate() {
    currentX.value = lerp(currentX.value, targetX.value, 0.05);
    currentY.value = lerp(currentY.value, targetY.value, 0.05);

    rafId = requestAnimationFrame(animate);
}

function onGlobalMouseMove(e: MouseEvent) {
    if (!heroRef.value) return;

    const rect = heroRef.value.getBoundingClientRect();
    if (
        e.clientX > rect.x + rect.width ||
        e.clientY > rect.y + rect.height ||
        e.clientX < rect.x ||
        e.clientY < rect.y
    ) {
        targetX.value = 0;
        targetY.value = 0;
        return;
    }

    const centerX = rect.left + rect.width / 2;
    const centerY = rect.top + rect.height / 2;

    // Set the target coordinates
    targetX.value = (e.clientX - centerX) / 30;
    targetY.value = (e.clientY - centerY) / 30;
}

onMounted(() => {
    window.addEventListener('mousemove', onGlobalMouseMove);
    animate();
});

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
        transition: transform 0.25 ease-out;
        transform: scale(1.25);
    }
}

#content {
    color: $white;
}
</style>
