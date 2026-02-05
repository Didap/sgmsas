<script setup lang="ts">
import { Button } from '@/components/ui/button'
import { Badge } from '@/components/ui/badge'
import { ArrowRight, Shield, Clock, Headphones } from 'lucide-vue-next'
</script>

<template>
  <section class="relative overflow-hidden pt-20 sm:pt-24">
    <!-- Background pattern -->
    <div class="absolute inset-0 bg-gradient-to-br from-primary/[0.03] via-transparent to-accent/[0.05]" />
    <div class="absolute top-0 right-0 w-1/2 h-full bg-gradient-to-l from-secondary/50 to-transparent" />

    <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16 sm:py-24 lg:py-32">
      <div class="grid lg:grid-cols-2 gap-12 lg:gap-16 items-center">
        <!-- Text Content -->
        <div class="space-y-8">
          <div>
            <Badge variant="secondary" class="mb-6 px-4 py-1.5 text-xs font-medium tracking-wide uppercase">
              <Shield class="w-3.5 h-3.5 mr-1.5" />
              Da oltre 20 anni al vostro servizio
            </Badge>

            <h1 class="font-display text-4xl sm:text-5xl lg:text-6xl font-bold text-foreground leading-[1.1] tracking-tight">
              Soluzioni per il
              <span class="text-accent">punto cassa</span>
              e l'informatica
            </h1>

            <p class="mt-6 text-lg sm:text-xl text-muted-foreground leading-relaxed max-w-xl">
              Vendita, installazione e assistenza tecnica per registratori di cassa, POS digitali, software gestionali e soluzioni informatiche complete per la tua attivit&agrave;.
            </p>
          </div>

          <div class="flex flex-col sm:flex-row gap-4">
            <Button size="lg" class="text-base px-8 h-12" as-child>
              <a href="#contatti">
                Richiedi un Preventivo
                <ArrowRight class="w-4 h-4 ml-2" />
              </a>
            </Button>
            <Button size="lg" variant="outline" class="text-base px-8 h-12" as-child>
              <a href="tel:3496709962">
                Chiama Ora
              </a>
            </Button>
          </div>

          <div class="flex flex-wrap gap-6 pt-2">
            <div class="flex items-center gap-2 text-sm text-muted-foreground">
              <Clock class="w-4 h-4 text-accent" />
              Interventi rapidi
            </div>
            <div class="flex items-center gap-2 text-sm text-muted-foreground">
              <Shield class="w-4 h-4 text-accent" />
              Assistenza certificata
            </div>
            <div class="flex items-center gap-2 text-sm text-muted-foreground">
              <Headphones class="w-4 h-4 text-accent" />
              Supporto dedicato
            </div>
          </div>
        </div>

        <!-- Hero Image Placeholder -->
        <div class="relative">
          <div class="aspect-[4/3] rounded-2xl bg-gradient-to-br from-secondary to-muted border border-border overflow-hidden flex items-center justify-center">
            <div class="text-center p-8 space-y-3">
              <div class="w-20 h-20 mx-auto rounded-full bg-primary/10 flex items-center justify-center">
                <svg class="w-10 h-10 text-primary/40" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
                  <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 15.75 5.159-5.159a2.25 2.25 0 0 1 3.182 0l5.159 5.159m-1.5-1.5 1.409-1.409a2.25 2.25 0 0 1 3.182 0l2.909 2.909M3.75 21h16.5A2.25 2.25 0 0 0 22.5 18.75V5.25A2.25 2.25 0 0 0 20.25 3H3.75A2.25 2.25 0 0 0 1.5 5.25v13.5A2.25 2.25 0 0 0 3.75 21Z" />
                </svg>
              </div>
              <p class="text-sm text-muted-foreground font-medium">Foto negozio / team SGM SAS</p>
              <p class="text-xs text-muted-foreground/60">Dimensione consigliata: 800x600px</p>
            </div>
          </div>
          <!-- Decorative floating card -->
          <div class="absolute -bottom-4 -left-4 sm:-bottom-6 sm:-left-6 bg-white rounded-xl shadow-lg border border-border p-4 sm:p-5">
            <div class="flex items-center gap-3">
              <div class="w-10 h-10 rounded-full bg-green-100 flex items-center justify-center flex-shrink-0">
                <svg class="w-5 h-5 text-green-600" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                  <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
                </svg>
              </div>
              <div>
                <div class="text-sm font-semibold text-foreground">+20 anni</div>
                <div class="text-xs text-muted-foreground">di esperienza</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
