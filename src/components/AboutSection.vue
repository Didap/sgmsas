<script setup lang="ts">
import { Badge } from '@/components/ui/badge'
import { Button } from '@/components/ui/button'
import { Separator } from '@/components/ui/separator'
import { CheckCircle2, ArrowRight } from 'lucide-vue-next'

const strengths = [
  'Vendita e assistenza registratori di cassa telematici',
  'Configurazione POS e sistemi di pagamento elettronico',
  'Installazione software gestionali personalizzati',
  'Fornitura computer, stampanti e periferiche professionali',
  'Assistenza tecnica rapida in sede e presso il cliente',
  'Consulenza gratuita per la scelta della soluzione ideale',
]
</script>

<template>
  <section id="chi-siamo" class="py-20 sm:py-28 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid lg:grid-cols-2 gap-12 lg:gap-20 items-center">
        <!-- Image Side -->
        <div class="relative order-2 lg:order-1">
          <div class="aspect-[5/4] rounded-2xl bg-gradient-to-br from-secondary to-muted border border-border overflow-hidden">
            <img src="/main2.webp" alt="SGM SAS - Team e laboratorio" class="w-full h-full object-cover" />
          </div>
          <!-- Accent detail -->
          <div class="absolute -z-10 -top-4 -left-4 w-full h-full rounded-2xl bg-primary/5 border border-primary/10" />
        </div>

        <!-- Text Side -->
        <div class="space-y-8 order-1 lg:order-2">
          <div>
            <Badge variant="outline" class="mb-4 px-4 py-1.5 text-xs font-medium tracking-wide uppercase">
              Chi Siamo
            </Badge>
            <h2 class="font-display text-3xl sm:text-4xl font-bold text-foreground tracking-tight">
              Da oltre 20 anni, il vostro partner tecnologico di fiducia
            </h2>
            <p class="mt-5 text-muted-foreground leading-relaxed text-lg">
              <strong class="text-foreground">SGM SAS di Angelo Pipino</strong> opera nel settore della vendita e assistenza di registratori di cassa e soluzioni informatiche dal cuore di Brindisi.
            </p>
            <p class="mt-4 text-muted-foreground leading-relaxed">
              Con un'esperienza ventennale, siamo diventati un punto di riferimento per commercianti, ristoratori, professionisti e aziende del territorio che cercano affidabilit&agrave;, competenza e un servizio post-vendita di qualit&agrave; superiore.
            </p>
            <p class="mt-4 text-muted-foreground leading-relaxed">
              La nostra missione &egrave; semplice: fornire tecnologia che funziona, con un'assistenza che non vi lascia mai soli. Ogni soluzione viene studiata su misura per le specifiche esigenze del cliente.
            </p>
          </div>

          <Separator />

          <ul class="space-y-3">
            <li
              v-for="strength in strengths"
              :key="strength"
              class="flex items-start gap-3"
            >
              <CheckCircle2 class="w-5 h-5 text-green-600 flex-shrink-0 mt-0.5" />
              <span class="text-sm text-foreground">{{ strength }}</span>
            </li>
          </ul>

          <Button size="lg" class="mt-4" as-child>
            <a href="#contatti">
              Scopri come possiamo aiutarti
              <ArrowRight class="w-4 h-4 ml-2" />
            </a>
          </Button>
        </div>
      </div>
    </div>
  </section>
</template>
