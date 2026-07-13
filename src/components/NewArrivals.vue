<script setup lang="ts">
import WorkCard from './WorkCard.vue'
const props = defineProps<{ works: any[] }>()
</script>

<template>
  <section id="new-arrivals">
    <div>
      <div class="uppercase">New arrivals</div>
      <h2 class="font-semibold">Fresh downloads</h2>
      <p>Recent works ready for your next session.</p>
      <div class="grid gap-3 grid-cols-2">
        <WorkCard v-for="w in props.works" :key="w.id" :work="w" />
      </div>
    </div>
  </section>
</template>
