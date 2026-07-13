<script setup lang="ts">
interface Work {
  id: string
  title: string
  author: string
  description: string
  url: string
  image: string
}
const props = defineProps<{ work: Work }>()
</script>

<template>
  <article class="border p-3">
    <div class="aspect-[4/5] overflow-hidden">
      <img :src="props.work.image" :alt="props.work.title" class="h-full w-full object-cover" />
    </div>
    <div class="p-2">
      <div class="uppercase">{{ props.work.author }}</div>
      <h3 class="font-semibold">{{ props.work.title }}</h3>
      <p>{{ props.work.description }}</p>
      <div class="flex justify-between items-center">
        <a :href="props.work.url">Download</a>
        <span class="uppercase">PDF</span>
      </div>
    </div>
  </article>
</template>
