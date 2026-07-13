<script setup lang="ts">
import { works } from '@/data'
import Header from '@/components/Header.vue'
import Featured from '@/components/Featured.vue'
import NewArrivals from '@/components/NewArrivals.vue'
import AllWorks from '@/components/AllWorks.vue'

const featuredWork = works[0]
const newArrivals = works.slice(0, 3)
const allWorks = works
</script>

<template>
  <div class="min-h-screen bg-white">
    <Header />

    <main class="mx-auto max-w-7xl px-4 py-8">
      <div class="grid gap-6 grid-cols-[1.45fr_1fr]">
        <Featured :work="featuredWork" />

        <div class="grid gap-3">
          <section class="border p-3">
            <p class="uppercase">Spotlight</p>
            <h2 class="font-semibold">Start something new</h2>
            <p>
              Share your scenarios, bestiary, or short fiction with direct download links.
            </p>
            <div class="flex gap-2">
              <a href="#all-works">Browse catalogue</a>
              <a href="#new-arrivals">Latest releases</a>
            </div>
          </section>

          <section class="border p-3">
            <p class="uppercase">Quick notes</p>
            <ul class="space-y-2">
              <li>High-quality one-sheet downloads for sessions and worldbuilding.</li>
              <li>
                Organized categories for new arrivals, featured works, and full library access.
              </li>
              <li>Lightweight layout designed for fast browsing and easy downloads.</li>
            </ul>
          </section>
        </div>
      </div>

      <NewArrivals :works="newArrivals" />

      <AllWorks :works="allWorks" />
    </main>
  </div>
</template>

<style lang="css">
@import 'tailwindcss';
</style>
