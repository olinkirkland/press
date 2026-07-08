<template>
  <div class="card">
    <div v-if="$slots.header">
      <div class="p-5">
        <slot name="header"></slot>
      </div>
      <hr class="mx-5" />
    </div>
    <div class="p-5">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.card {
  background-color: white;
  border-radius: 5px;
  overflow: hidden;
}
</style>
