<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle, CardDescription } from '@/components/ui/card'
import { Badge } from '@/components/ui/badge'
import { ArrowRight, Monitor, Calculator, BarChart3, Laptop, Wrench, Wifi } from 'lucide-vue-next'

const services = [
  {
    icon: Calculator,
    title: 'Registratori di Cassa',
    description: 'Fornitura e installazione di registratori di cassa fiscali di ultima generazione. Conformi alla normativa vigente con invio telematico dei corrispettivi all\'Agenzia delle Entrate.',
    features: ['Registratori telematici', 'Invio corrispettivi', 'Conformi normativa'],
    badge: 'Servizio principale',
  },
  {
    icon: Monitor,
    title: 'Casse Digitali Touch Screen',
    description: 'Sistemi touch screen completi per ristoranti, bar, negozi e attivit\u00e0 commerciali. Soluzioni personalizzate con hardware e software integrati per ogni esigenza.',
    features: ['POS touch screen', 'Sistemi completi', 'Soluzioni su misura'],
    badge: null,
  },
  {
    icon: BarChart3,
    title: 'Software Gestionali',
    description: 'Implementazione e configurazione di software gestionali per la gestione completa della tua attivit\u00e0: magazzino, fatturazione elettronica, contabilit\u00e0 e analisi vendite.',
    features: ['Fatturazione elettronica', 'Gestione magazzino', 'Report vendite'],
    badge: null,
  },
  {
    icon: Laptop,
    title: 'Computer e Informatica',
    description: 'Vendita, configurazione e assistenza su PC desktop, notebook, server, reti e periferiche. Soluzioni informatiche professionali per ufficio e azienda.',
    features: ['PC e notebook', 'Server e reti', 'Periferiche'],
    badge: null,
  },
  {
    icon: Wrench,
    title: 'Assistenza Tecnica',
    description: 'Servizio di assistenza tecnica qualificata su tutti i prodotti venduti. Interventi rapidi in laboratorio e presso la sede del cliente per minimizzare i tempi di fermo.',
    features: ['In sede e da remoto', 'Tempi rapidi', 'Tecnici qualificati'],
    badge: 'Priorit\u00e0',
  },
  {
    icon: Wifi,
    title: 'Reti e Connettivit\u00e0',
    description: 'Progettazione e installazione di reti LAN, Wi-Fi e soluzioni di connettivit\u00e0 per uffici e attivit\u00e0 commerciali. Sicurezza e performance garantite.',
    features: ['Reti LAN/Wi-Fi', 'Sicurezza', 'Configurazione'],
    badge: null,
  },
]
</script>

<template>
  <section id="servizi" class="py-20 sm:py-28 bg-background">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section Header -->
      <div class="max-w-2xl mx-auto text-center mb-14 sm:mb-20">
        <Badge variant="outline" class="mb-4 px-4 py-1.5 text-xs font-medium tracking-wide uppercase">
          I Nostri Servizi
        </Badge>
        <h2 class="font-display text-3xl sm:text-4xl lg:text-5xl font-bold text-foreground tracking-tight">
          Tutto ci&ograve; che serve alla tua attivit&agrave;
        </h2>
        <p class="mt-4 text-lg text-muted-foreground leading-relaxed">
          Offriamo una gamma completa di prodotti e servizi per la gestione del punto cassa e le esigenze informatiche della tua impresa.
        </p>
      </div>

      <!-- Services Grid -->
      <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6 sm:gap-8">
        <Card
          v-for="service in services"
          :key="service.title"
          class="group relative overflow-hidden transition-all duration-300 hover:shadow-lg hover:-translate-y-1 hover:border-accent/30"
        >
          <CardHeader class="pb-4">
            <div class="flex items-start justify-between mb-3">
              <div class="w-12 h-12 rounded-lg bg-primary/5 flex items-center justify-center group-hover:bg-primary/10 transition-colors">
                <component :is="service.icon" class="w-6 h-6 text-primary" />
              </div>
              <Badge v-if="service.badge" variant="secondary" class="text-xs">{{ service.badge }}</Badge>
            </div>
            <CardTitle class="text-xl font-semibold">{{ service.title }}</CardTitle>
            <CardDescription class="text-sm leading-relaxed mt-2">{{ service.description }}</CardDescription>
          </CardHeader>
          <CardContent>
            <div class="flex flex-wrap gap-2 mb-4">
              <span
                v-for="feature in service.features"
                :key="feature"
                class="inline-flex items-center px-2.5 py-1 text-xs font-medium bg-secondary text-secondary-foreground rounded-md"
              >
                {{ feature }}
              </span>
            </div>
            <a
              href="#contatti"
              class="inline-flex items-center text-sm font-medium text-accent hover:text-accent/80 transition-colors group/link"
            >
              Richiedi informazioni
              <ArrowRight class="w-3.5 h-3.5 ml-1.5 transition-transform group-hover/link:translate-x-1" />
            </a>
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>
