<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle, CardDescription } from '@/components/ui/card'
import { Badge } from '@/components/ui/badge'
import { Button } from '@/components/ui/button'
import { ArrowRight } from 'lucide-vue-next'

const products = [
  {
    category: 'Registratori Telematici',
    title: 'Registratori di Cassa',
    description: 'Registratori telematici di ultima generazione, conformi alla normativa per l\'invio dei corrispettivi. Modelli compatti e professionali per ogni tipo di attivit\u00e0.',
    image: '/cassa.webp',
    placeholder: 'Foto registratore di cassa',
    size: '400x300px',
    badge: 'Bestseller',
  },
  {
    category: 'Sistemi POS',
    title: 'POS Touch Screen',
    description: 'Sistemi punto cassa completi con display touch, cassetto portamonete, stampante e software gestionale integrato. Ideali per ristorazione e retail.',
    image: '/touch.webp',
    placeholder: 'Foto sistema POS touch screen',
    size: '400x300px',
    badge: 'Novit\u00e0',
  },
  {
    category: 'Software',
    title: 'Gestionali Professionali',
    description: 'Software per la gestione completa dell\'attivit\u00e0: magazzino, fatturazione elettronica, prima nota, analisi delle vendite e molto altro.',
    image: '/gestionale.webp',
    placeholder: 'Screenshot software gestionale',
    size: '400x300px',
    badge: null,
  },
  {
    category: 'Hardware',
    title: 'PC, Notebook e Stampanti',
    description: 'Ampia selezione di computer desktop, notebook, stampanti e periferiche dei migliori marchi. Configurazioni su misura per professionisti e aziende.',
    image: '/hardware.webp',
    placeholder: 'Foto computer e periferiche',
    size: '400x300px',
    badge: null,
  },
]
</script>

<template>
  <section id="prodotti" class="py-20 sm:py-28 bg-background">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section Header -->
      <div class="max-w-2xl mx-auto text-center mb-14 sm:mb-20">
        <Badge variant="outline" class="mb-4 px-4 py-1.5 text-xs font-medium tracking-wide uppercase">
          I Nostri Prodotti
        </Badge>
        <h2 class="font-display text-3xl sm:text-4xl lg:text-5xl font-bold text-foreground tracking-tight">
          Tecnologia selezionata per il tuo business
        </h2>
        <p class="mt-4 text-lg text-muted-foreground leading-relaxed">
          Selezioniamo i migliori prodotti sul mercato per offrirti soluzioni affidabili e durature. Ogni prodotto viene installato e configurato dai nostri tecnici.
        </p>
      </div>

      <!-- Products Grid -->
      <div class="grid sm:grid-cols-2 gap-8">
        <Card
          v-for="product in products"
          :key="product.title"
          class="overflow-hidden group hover:shadow-lg transition-all duration-300"
        >
          <!-- Image -->
          <div class="aspect-[4/3] bg-gradient-to-br from-secondary to-muted border-b border-border flex items-center justify-center relative overflow-hidden">
            <img
              v-if="product.image"
              :src="product.image"
              :alt="product.title"
              class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105"
            />
            <div v-else class="text-center p-6 space-y-2">
              <div class="w-16 h-16 mx-auto rounded-full bg-primary/10 flex items-center justify-center">
                <svg class="w-8 h-8 text-primary/40" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
                  <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 15.75 5.159-5.159a2.25 2.25 0 0 1 3.182 0l5.159 5.159m-1.5-1.5 1.409-1.409a2.25 2.25 0 0 1 3.182 0l2.909 2.909M3.75 21h16.5A2.25 2.25 0 0 0 22.5 18.75V5.25A2.25 2.25 0 0 0 20.25 3H3.75A2.25 2.25 0 0 0 1.5 5.25v13.5A2.25 2.25 0 0 0 3.75 21Z" />
                </svg>
              </div>
              <p class="text-sm text-muted-foreground font-medium">{{ product.placeholder }}</p>
              <p class="text-xs text-muted-foreground/60">{{ product.size }}</p>
            </div>
            <Badge
              v-if="product.badge"
              class="absolute top-4 right-4"
            >
              {{ product.badge }}
            </Badge>
          </div>

          <CardHeader>
            <p class="text-xs font-medium text-accent uppercase tracking-wider mb-1">{{ product.category }}</p>
            <CardTitle class="text-xl">{{ product.title }}</CardTitle>
            <CardDescription class="leading-relaxed">{{ product.description }}</CardDescription>
          </CardHeader>

          <CardContent>
            <Button variant="outline" size="sm" class="group/btn" as-child>
              <a href="#contatti">
                Richiedi Informazioni
                <ArrowRight class="w-3.5 h-3.5 ml-1.5 transition-transform group-hover/btn:translate-x-1" />
              </a>
            </Button>
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>
