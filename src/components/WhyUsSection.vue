<script setup lang="ts">
import { Card, CardContent } from '@/components/ui/card'
import { Badge } from '@/components/ui/badge'
import { Award, HeartHandshake, Zap, ShieldCheck, Users, Settings } from 'lucide-vue-next'

const reasons = [
  {
    icon: Award,
    title: 'Esperienza Ventennale',
    description: 'Oltre 20 anni di presenza sul territorio significano conoscenza profonda del settore e soluzioni collaudate.',
  },
  {
    icon: HeartHandshake,
    title: 'Rapporto Diretto',
    description: 'Nessun call center: parli direttamente con i tecnici che conoscono la tua attivit\u00e0 e le tue esigenze.',
  },
  {
    icon: Zap,
    title: 'Interventi Rapidi',
    description: 'Sappiamo che un fermo cassa significa perdita di fatturato. Interveniamo tempestivamente per ridurre al minimo i disagi.',
  },
  {
    icon: ShieldCheck,
    title: 'Conformit\u00e0 Garantita',
    description: 'Tutti i nostri registratori telematici sono conformi alla normativa fiscale vigente e certificati per l\'invio dei corrispettivi.',
  },
  {
    icon: Users,
    title: 'Formazione Inclusa',
    description: 'Non ti lasciamo solo: ogni installazione include la formazione del personale per utilizzare al meglio la tecnologia.',
  },
  {
    icon: Settings,
    title: 'Soluzioni Su Misura',
    description: 'Analizziamo le tue esigenze specifiche per proporti la configurazione ideale, senza farti spendere di pi\u00f9 del necessario.',
  },
]
</script>

<template>
  <section class="py-20 sm:py-28 bg-secondary/50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section Header -->
      <div class="max-w-2xl mx-auto text-center mb-14 sm:mb-20">
        <Badge variant="outline" class="mb-4 px-4 py-1.5 text-xs font-medium tracking-wide uppercase bg-white">
          Perch&eacute; Sceglierci
        </Badge>
        <h2 class="font-display text-3xl sm:text-4xl lg:text-5xl font-bold text-foreground tracking-tight">
          La differenza &egrave; nel servizio
        </h2>
        <p class="mt-4 text-lg text-muted-foreground leading-relaxed">
          Non vendiamo solo prodotti: costruiamo relazioni di fiducia con i nostri clienti, offrendo un servizio completo dalla consulenza iniziale all'assistenza post-vendita.
        </p>
      </div>

      <!-- Reasons Grid -->
      <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6 sm:gap-8">
        <Card
          v-for="reason in reasons"
          :key="reason.title"
          class="bg-white border-border/60 hover:shadow-md transition-all duration-300"
        >
          <CardContent class="pt-6 pb-6">
            <div class="w-11 h-11 rounded-lg bg-accent/10 flex items-center justify-center mb-4">
              <component :is="reason.icon" class="w-5 h-5 text-accent" />
            </div>
            <h3 class="text-lg font-semibold text-foreground mb-2">{{ reason.title }}</h3>
            <p class="text-sm text-muted-foreground leading-relaxed">{{ reason.description }}</p>
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>
