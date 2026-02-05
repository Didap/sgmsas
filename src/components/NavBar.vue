<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import { Button } from '@/components/ui/button'
import { Menu, X, Phone } from 'lucide-vue-next'

const isScrolled = ref(false)
const mobileMenuOpen = ref(false)

const navLinks = [
  { label: 'Servizi', href: '#servizi' },
  { label: 'Chi Siamo', href: '#chi-siamo' },
  { label: 'Prodotti', href: '#prodotti' },
  { label: 'Contatti', href: '#contatti' },
]

function handleScroll() {
  isScrolled.value = window.scrollY > 20
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<template>
  <header
    :class="[
      'fixed top-0 left-0 right-0 z-50 transition-all duration-300',
      isScrolled
        ? 'bg-white/95 backdrop-blur-md shadow-sm border-b border-border'
        : 'bg-transparent'
    ]"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16 sm:h-20">
        <!-- Logo -->
        <a href="#" class="flex items-center gap-3 group">
          <div class="w-10 h-10 sm:w-12 sm:h-12 rounded-lg bg-primary flex items-center justify-center transition-transform group-hover:scale-105">
            <span class="text-primary-foreground font-bold text-sm sm:text-base tracking-tight">SGM</span>
          </div>
          <div class="hidden sm:block">
            <div class="font-display text-lg font-bold text-foreground leading-tight">SGM SAS</div>
            <div class="text-xs text-muted-foreground leading-tight">di Angelo Pipino</div>
          </div>
        </a>

        <!-- Desktop Nav -->
        <nav class="hidden md:flex items-center gap-1">
          <a
            v-for="link in navLinks"
            :key="link.href"
            :href="link.href"
            class="px-4 py-2 text-sm font-medium text-muted-foreground hover:text-foreground transition-colors rounded-md hover:bg-secondary"
          >
            {{ link.label }}
          </a>
        </nav>

        <!-- Desktop CTA -->
        <div class="hidden md:flex items-center gap-3">
          <a href="tel:3496709962" class="flex items-center gap-2 text-sm font-medium text-muted-foreground hover:text-foreground transition-colors">
            <Phone class="w-4 h-4" />
            349 6709962
          </a>
          <Button as-child>
            <a href="#contatti">Richiedi Preventivo</a>
          </Button>
        </div>

        <!-- Mobile Menu Toggle -->
        <button
          class="md:hidden p-2 rounded-md hover:bg-secondary transition-colors"
          @click="mobileMenuOpen = !mobileMenuOpen"
        >
          <Menu v-if="!mobileMenuOpen" class="w-6 h-6" />
          <X v-else class="w-6 h-6" />
        </button>
      </div>
    </div>

    <!-- Mobile Menu -->
    <Transition
      enter-active-class="transition-all duration-200 ease-out"
      enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition-all duration-150 ease-in"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-2"
    >
      <div v-if="mobileMenuOpen" class="md:hidden bg-white/95 backdrop-blur-md border-b border-border">
        <div class="px-4 py-4 space-y-1">
          <a
            v-for="link in navLinks"
            :key="link.href"
            :href="link.href"
            class="block px-4 py-3 text-sm font-medium text-muted-foreground hover:text-foreground hover:bg-secondary rounded-md transition-colors"
            @click="mobileMenuOpen = false"
          >
            {{ link.label }}
          </a>
          <div class="pt-3 border-t border-border mt-3 space-y-2">
            <a href="tel:3496709962" class="flex items-center gap-2 px-4 py-3 text-sm font-medium text-muted-foreground">
              <Phone class="w-4 h-4" />
              349 6709962
            </a>
            <Button class="w-full" as-child>
              <a href="#contatti" @click="mobileMenuOpen = false">Richiedi Preventivo</a>
            </Button>
          </div>
        </div>
      </div>
    </Transition>
  </header>
</template>
