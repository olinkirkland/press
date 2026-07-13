<script setup lang="ts">
const props = defineProps<{ work: any }>()
</script>

<template>
  <section class="border p-4">
    <div>
      <div class="uppercase">Featured release</div>
      <h1 class="font-semibold">{{ props.work.title }}</h1>
      <p>{{ props.work.description }}</p>
      <div class="flex gap-2">
        <a :href="props.work.url">Download</a>
        <a href="#new-arrivals">See new arrivals</a>
      </div>
      <div class="grid grid-cols-2 gap-2">
        <div class="border p-2">
          <div class="uppercase">Author</div>
          <div class="font-semibold">{{ props.work.author }}</div>
        </div>
        <div class="border p-2">
          <div class="uppercase">Format</div>
          <div class="font-semibold">PDF download</div>
        </div>
      </div>
    </div>
  </section>
</template>
