<template>
    <button
        class="cursor-pointer flex gap-1.5 items-center rounded-sm"
        :class="{
            'px-1 h-6': props.size === 'sm',
            'px-3 h-10': props.size === 'md',
            'px-5 h-15': props.size === 'lg',
        }"
    >
        <slot></slot>
    </button>
</template>

<style lang="scss" scoped>
button {
    color: $black;
    background-color: rgba(255, 255, 255, 0.75);
    text-transform: uppercase;
    font-size: 0.75rem;
    line-height: 1;
    letter-spacing: 2px;
    transition: 0.2s all;
    align-self: flex-start;
    backdrop-filter: blur(5px);

    &:hover {
        background-color: rgba(255, 255, 255, 0.9);
    }

    &:active {
        transition: none;
        background-color: rgba(255, 255, 255, 0.7);
    }
}

:deep(img) {
    width: 1rem;
    height: 1rem;
}
</style>

<script lang="ts" setup>
const props = withDefaults(
    defineProps<{
        size?: 'sm' | 'md' | 'lg';
    }>(),
    {
        size: 'md',
    },
);
</script>
