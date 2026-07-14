<template>
    <button class="px-5 h-10 cursor-pointer flex gap-1.5 items-center rounded-sm">
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
    transition: 0.2s background-color;
    align-self: flex-start;

    &:hover {
        background-color: rgba(255, 255, 255, 0.85);
    }
}

:deep(img) {
    width: 1rem;
    height: 1rem;
}
</style>
