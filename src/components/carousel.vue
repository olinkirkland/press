<template>
    <div class="carousel flex flex-col gap-2 mb-10">
        <div class="image-container overflow-hidden relative">
            <Transition :name="slideDirection" mode="out-in">
                <img
                    class="w-full h-full object-cover"
                    :key="carouselIndex"
                    :src="`images/hero/${currentCarouselContent?.image}`"
                    :alt="`images/hero/${currentCarouselContent?.image}`"
                />
            </Transition>
            <!-- <ul class="absolute bottom-0 w-full flex gap-1 ml-2">
                <li
                    v-for="(dot, index) in data"
                    class="dot cursor-pointer"
                    :class="{ 'dot--selected': carouselIndex === index }"
                    @click="setCarouselIndex(index)"
                ></li>
            </ul> -->
        </div>

        <div class="flex justify-between gap-md items-end">
            <div class="flex flex-shrink-0">
                <button @click="changeCarouselIndex(1)" class="carousel-button opacity-90">
                    <img class="w-10 rotate-180" src="../assets/icons/white/arrow-circle.png" />
                </button>
                <button @click="changeCarouselIndex(-1)" class="carousel-button opacity-90">
                    <img class="w-10" src="../assets/icons/white/arrow-circle.png" />
                </button>
            </div>
            <small class="text-right">
                <span v-html="currentCarouselContent?.description"></span>
                <a :href="currentCarouselContent?.link" class="ml-1">Read more</a>
            </small>
        </div>
    </div>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue';

export type CarouselContent = {
    title: string;
    tags: string[];
    description: string;
    image: string;
    link: string;
};

const props = defineProps<{
    data: CarouselContent[];
}>();

const carouselIndex = ref(0);
const slideDirection = ref('slide-next');
const currentCarouselContent = computed(() => props.data[carouselIndex.value]);

function changeCarouselIndex(n: number) {
    // Set transition direction based on forward (1) or backward (-1)
    slideDirection.value = n > 0 ? 'slide-next' : 'slide-prev';

    carouselIndex.value += n;
    if (carouselIndex.value < 0) carouselIndex.value = props.data.length - 1;
    if (carouselIndex.value > props.data.length - 1) carouselIndex.value = 0;
}

function setCarouselIndex(n: number) {
    carouselIndex.value = n;
}
</script>

<style lang="scss" scoped>
.carousel {
    width: 30rem;
    height: 30rem;
    margin-top: 5rem;

    .image-container {
        flex: 1;
        position: relative;
    }

    .description-text {
        display: -webkit-box;
        -webkit-box-orient: vertical;
        -webkit-line-clamp: 2;
        line-clamp: 2;
        overflow: hidden;
        text-overflow: ellipsis;
    }
}

.carousel-button {
    &:hover {
        opacity: 1;
    }
    &:active {
        opacity: 0.5;
    }
}

.dot {
    border: 1px solid white;
    border-radius: 100%;
    width: 0.8rem;
    height: 0.8rem;
    &--selected {
        background-color: white;
    }
}

/* Slide Next Transitions */
.slide-next-enter-active,
.slide-next-leave-active {
    transition: all 0.3s;
}
.slide-next-enter-from {
    transform: translateX(-2%);
    opacity: 1;
}
.slide-next-leave-to {
    transform: translateX(2%);
    opacity: 0;
}

/* Slide Prev Transitions */
.slide-prev-enter-active,
.slide-prev-leave-active {
    transition: all 0.3s;
}
.slide-prev-enter-from {
    transform: translateX(2%);
    opacity: 1;
}
.slide-prev-leave-to {
    transform: translateX(-2%);
    opacity: 0;
}
</style>
