<script setup lang="ts">
import WorkCard from './WorkCard.vue'
const props = defineProps<{ works: any[] }>()
</script>

<template>
  <section id="all-works">
    <div>
      <h2 class="font-semibold">All works</h2>
      <p>Complete library of published downloads and scenario bundles.</p>
      <div class="grid gap-3 grid-cols-2">
        <WorkCard v-for="w in props.works" :key="w.id" :work="w" />
      </div>
    </div>
  </section>
</template>
