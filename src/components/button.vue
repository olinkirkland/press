<template>
    <button class="px-2 py-1 cursor-pointer flex gap-1.5 items-center rounded-sm">
        <slot></slot>
    </button>
</template>

<style lang="scss" scoped>
button {
    color: $black;
    background-color: rgba(255, 255, 255, 0.25);
    text-transform: uppercase;
    font-size: x-small;
    letter-spacing: 2px;
    transition: 0.2s background-color;

    &:hover {
        background-color: rgba(255, 255, 255, 0.5);
    }
}

:deep(img) {
    width: 1rem;
    height: 1rem;
}
</style>
