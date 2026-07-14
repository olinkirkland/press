<template>
    <button class="p-0 cursor-pointer flex items-center">
        <slot></slot>
    </button>
</template>

<style lang="scss" scoped>
button {
    position: relative;
    color: $white;
    &::after {
        position: absolute;
        content: '';
        width: 100%;
        height: 1px;
        bottom: 0;
        left: 0;
        background-color: $white;
        transform: scaleX(0);
        transform-origin: bottom center;
        transition: transform 0.2s ease-out;
    }
    &:hover::after {
        transform: scaleX(1);
    }
}

:deep(img) {
    height: 1.5rem;
}
</style>
