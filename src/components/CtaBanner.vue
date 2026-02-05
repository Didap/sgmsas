<script setup lang="ts">
import { Button } from '@/components/ui/button'
import { Phone, ArrowRight } from 'lucide-vue-next'
</script>

<template>
  <section class="py-16 sm:py-20 bg-primary text-primary-foreground relative overflow-hidden">
    <!-- Subtle pattern -->
    <div class="absolute inset-0 opacity-[0.04]" style="background-image: radial-gradient(circle at 1px 1px, currentColor 1px, transparent 0); background-size: 32px 32px;" />

    <div class="relative max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
      <h2 class="font-display text-3xl sm:text-4xl lg:text-5xl font-bold tracking-tight leading-tight">
        Hai bisogno di un registratore di cassa o di assistenza informatica?
      </h2>
      <p class="mt-5 text-lg sm:text-xl text-primary-foreground/80 max-w-2xl mx-auto leading-relaxed">
        Contattaci oggi stesso per un preventivo gratuito e senza impegno. I nostri tecnici sono pronti ad aiutarti a trovare la soluzione perfetta per la tua attivit&agrave;.
      </p>
      <div class="mt-8 flex flex-col sm:flex-row justify-center gap-4">
        <Button
          size="lg"
          variant="secondary"
          class="text-base px-8 h-12"
          as-child
        >
          <a href="#contatti">
            Richiedi Preventivo Gratuito
            <ArrowRight class="w-4 h-4 ml-2" />
          </a>
        </Button>
        <Button
          size="lg"
          variant="outline"
          class="text-base px-8 h-12 border-primary-foreground/30 text-primary-foreground hover:bg-primary-foreground/10 hover:text-primary-foreground"
          as-child
        >
          <a href="tel:3496709962">
            <Phone class="w-4 h-4 mr-2" />
            Chiama 349 6709962
          </a>
        </Button>
      </div>
    </div>
  </section>
</template>
