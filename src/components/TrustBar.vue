<script setup lang="ts">
const stats = [
  { number: '20+', label: 'Anni di Esperienza' },
  { number: '1000+', label: 'Clienti Soddisfatti' },
  { number: '5000+', label: 'Installazioni' },
  { number: '24h', label: 'Assistenza Rapida' },
]
</script>

<template>
  <section class="border-y border-border bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 sm:py-10">
      <div class="grid grid-cols-2 lg:grid-cols-4 gap-6 sm:gap-8">
        <div
          v-for="stat in stats"
          :key="stat.label"
          class="text-center"
        >
          <div class="text-3xl sm:text-4xl font-display font-bold text-primary">{{ stat.number }}</div>
          <div class="mt-1 text-sm text-muted-foreground">{{ stat.label }}</div>
        </div>
      </div>
    </div>
  </section>
</template>
