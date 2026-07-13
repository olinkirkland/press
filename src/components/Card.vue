<template>
  <div class="overflow-hidden border bg-white">
    <div v-if="$slots.header" class="border-b">
      <div class="p-2">
        <slot name="header"></slot>
      </div>
    </div>
    <div class="p-2">
      <slot />
    </div>
  </div>
</template>
