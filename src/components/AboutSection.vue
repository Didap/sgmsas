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
          <div class="aspect-[5/4] rounded-2xl bg-gradient-to-br from-secondary to-muted border border-border overflow-hidden flex items-center justify-center">
            <div class="text-center p-8 space-y-3">
              <div class="w-20 h-20 mx-auto rounded-full bg-primary/10 flex items-center justify-center">
                <svg class="w-10 h-10 text-primary/40" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
                  <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 15.75 5.159-5.159a2.25 2.25 0 0 1 3.182 0l5.159 5.159m-1.5-1.5 1.409-1.409a2.25 2.25 0 0 1 3.182 0l2.909 2.909M3.75 21h16.5A2.25 2.25 0 0 0 22.5 18.75V5.25A2.25 2.25 0 0 0 20.25 3H3.75A2.25 2.25 0 0 0 1.5 5.25v13.5A2.25 2.25 0 0 0 3.75 21Z" />
                </svg>
              </div>
              <p class="text-sm text-muted-foreground font-medium">Foto del team / laboratorio</p>
              <p class="text-xs text-muted-foreground/60">Dimensione consigliata: 800x640px</p>
            </div>
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
