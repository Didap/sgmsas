<script setup lang="ts">
import { Separator } from '@/components/ui/separator'
import { Phone, Mail, MapPin } from 'lucide-vue-next'
</script>

<template>
  <footer class="bg-foreground text-primary-foreground">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-14 sm:py-16">
      <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-10 lg:gap-12">
        <!-- Brand -->
        <div class="sm:col-span-2 lg:col-span-1">
          <div class="flex items-center gap-3 mb-4">
            <div class="w-10 h-10 rounded-lg bg-primary-foreground/10 flex items-center justify-center">
              <span class="text-primary-foreground font-bold text-sm">SGM</span>
            </div>
            <div>
              <div class="font-display text-lg font-bold leading-tight">SGM SAS</div>
              <div class="text-xs text-primary-foreground/60 leading-tight">di Angelo Pipino</div>
            </div>
          </div>
          <p class="text-sm text-primary-foreground/60 leading-relaxed">
            Da oltre 20 anni il vostro partner per registratori di cassa, soluzioni POS, software gestionali e assistenza informatica a Brindisi.
          </p>
        </div>

        <!-- Quick Links -->
        <div>
          <h3 class="text-sm font-semibold uppercase tracking-wider mb-4 text-primary-foreground/80">Navigazione</h3>
          <ul class="space-y-2.5">
            <li><a href="#servizi" class="text-sm text-primary-foreground/60 hover:text-primary-foreground transition-colors">Servizi</a></li>
            <li><a href="#chi-siamo" class="text-sm text-primary-foreground/60 hover:text-primary-foreground transition-colors">Chi Siamo</a></li>
            <li><a href="#prodotti" class="text-sm text-primary-foreground/60 hover:text-primary-foreground transition-colors">Prodotti</a></li>
            <li><a href="#contatti" class="text-sm text-primary-foreground/60 hover:text-primary-foreground transition-colors">Contatti</a></li>
          </ul>
        </div>

        <!-- Services -->
        <div>
          <h3 class="text-sm font-semibold uppercase tracking-wider mb-4 text-primary-foreground/80">Servizi</h3>
          <ul class="space-y-2.5">
            <li><a href="#servizi" class="text-sm text-primary-foreground/60 hover:text-primary-foreground transition-colors">Registratori di Cassa</a></li>
            <li><a href="#servizi" class="text-sm text-primary-foreground/60 hover:text-primary-foreground transition-colors">Casse Digitali e POS</a></li>
            <li><a href="#servizi" class="text-sm text-primary-foreground/60 hover:text-primary-foreground transition-colors">Software Gestionali</a></li>
            <li><a href="#servizi" class="text-sm text-primary-foreground/60 hover:text-primary-foreground transition-colors">Assistenza Tecnica</a></li>
          </ul>
        </div>

        <!-- Contact -->
        <div>
          <h3 class="text-sm font-semibold uppercase tracking-wider mb-4 text-primary-foreground/80">Contatti</h3>
          <ul class="space-y-3">
            <li class="flex items-start gap-2.5">
              <MapPin class="w-4 h-4 mt-0.5 flex-shrink-0 text-primary-foreground/40" />
              <span class="text-sm text-primary-foreground/60">
                Via Romagna, 53<br>72100 Brindisi (BR)
              </span>
            </li>
            <li class="flex items-center gap-2.5">
              <Phone class="w-4 h-4 flex-shrink-0 text-primary-foreground/40" />
              <a href="tel:3496709962" class="text-sm text-primary-foreground/60 hover:text-primary-foreground transition-colors">
                349 6709962
              </a>
            </li>
            <li class="flex items-center gap-2.5">
              <Mail class="w-4 h-4 flex-shrink-0 text-primary-foreground/40" />
              <a href="mailto:Sgmsasbrindisi@gmail.com" class="text-sm text-primary-foreground/60 hover:text-primary-foreground transition-colors break-all">
                Sgmsasbrindisi@gmail.com
              </a>
            </li>
          </ul>
        </div>
      </div>

      <Separator class="my-8 bg-primary-foreground/10" />

      <div class="flex flex-col sm:flex-row justify-between items-center gap-4">
        <p class="text-xs text-primary-foreground/40">
          &copy; {{ new Date().getFullYear() }} SGM SAS di Angelo Pipino &mdash; P.IVA 01512530740 &mdash; Tutti i diritti riservati.
        </p>
        <p class="text-xs text-primary-foreground/40">
          Via Romagna, 53 &mdash; 72100 Brindisi (BR)
        </p>
      </div>
    </div>
  </footer>
</template>
