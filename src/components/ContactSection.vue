<script setup lang="ts">
import { ref, computed } from 'vue'
import { Card, CardContent, CardHeader, CardTitle, CardDescription } from '@/components/ui/card'
import { Input } from '@/components/ui/input'
import { Textarea } from '@/components/ui/textarea'
import { Label } from '@/components/ui/label'
import { Button } from '@/components/ui/button'
import { Badge } from '@/components/ui/badge'
import { Send, Phone, Mail, MapPin, MessageCircle } from 'lucide-vue-next'

const form = ref({
  nome: '',
  email: '',
  telefono: '',
  oggetto: '',
  messaggio: '',
})

const mailtoLink = computed(() => {
  const subject = encodeURIComponent(form.value.oggetto || 'Richiesta informazioni dal sito web')
  const body = encodeURIComponent(
    `Nome: ${form.value.nome}\nEmail: ${form.value.email}\nTelefono: ${form.value.telefono}\n\n${form.value.messaggio}`
  )
  return `mailto:Sgmsasbrindisi@gmail.com?subject=${subject}&body=${body}`
})

function handleSubmit() {
  window.location.href = mailtoLink.value
}
</script>

<template>
  <section id="contatti" class="py-20 sm:py-28 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section Header -->
      <div class="max-w-2xl mx-auto text-center mb-14 sm:mb-20">
        <Badge variant="outline" class="mb-4 px-4 py-1.5 text-xs font-medium tracking-wide uppercase">
          Contattaci
        </Badge>
        <h2 class="font-display text-3xl sm:text-4xl lg:text-5xl font-bold text-foreground tracking-tight">
          Parliamo del tuo progetto
        </h2>
        <p class="mt-4 text-lg text-muted-foreground leading-relaxed">
          Compila il modulo per ricevere un preventivo gratuito, oppure contattaci direttamente per telefono o WhatsApp.
        </p>
      </div>

      <div class="grid lg:grid-cols-5 gap-10 lg:gap-16">
        <!-- Contact Form -->
        <div class="lg:col-span-3">
          <Card class="shadow-sm">
            <CardHeader>
              <CardTitle class="text-xl">Richiedi un Preventivo</CardTitle>
              <CardDescription>Compila tutti i campi e ti risponderemo al pi&ugrave; presto.</CardDescription>
            </CardHeader>
            <CardContent>
              <form @submit.prevent="handleSubmit" class="space-y-5">
                <div class="grid sm:grid-cols-2 gap-5">
                  <div class="space-y-2">
                    <Label for="nome">Nome e Cognome</Label>
                    <Input
                      id="nome"
                      v-model="form.nome"
                      placeholder="Mario Rossi"
                      required
                    />
                  </div>
                  <div class="space-y-2">
                    <Label for="email">Email</Label>
                    <Input
                      id="email"
                      type="email"
                      v-model="form.email"
                      placeholder="mario.rossi@email.com"
                      required
                    />
                  </div>
                </div>

                <div class="grid sm:grid-cols-2 gap-5">
                  <div class="space-y-2">
                    <Label for="telefono">Telefono</Label>
                    <Input
                      id="telefono"
                      type="tel"
                      v-model="form.telefono"
                      placeholder="+39 333 1234567"
                    />
                  </div>
                  <div class="space-y-2">
                    <Label for="oggetto">Oggetto</Label>
                    <Input
                      id="oggetto"
                      v-model="form.oggetto"
                      placeholder="es. Preventivo registratore di cassa"
                      required
                    />
                  </div>
                </div>

                <div class="space-y-2">
                  <Label for="messaggio">Messaggio</Label>
                  <Textarea
                    id="messaggio"
                    v-model="form.messaggio"
                    placeholder="Descrivi di cosa hai bisogno: tipo di attivit&agrave;, numero di casse, esigenze particolari..."
                    rows="5"
                    required
                  />
                </div>

                <Button type="submit" size="lg" class="w-full sm:w-auto px-8">
                  <Send class="w-4 h-4 mr-2" />
                  Invia Richiesta
                </Button>
              </form>
            </CardContent>
          </Card>
        </div>

        <!-- Contact Info -->
        <div class="lg:col-span-2 space-y-6">
          <!-- Phone -->
          <Card class="shadow-sm hover:shadow-md transition-shadow">
            <CardContent class="pt-6 pb-6">
              <div class="flex items-start gap-4">
                <div class="w-11 h-11 rounded-lg bg-primary/5 flex items-center justify-center flex-shrink-0">
                  <Phone class="w-5 h-5 text-primary" />
                </div>
                <div>
                  <h3 class="font-semibold text-foreground mb-1">Telefono</h3>
                  <a href="tel:3496709962" class="text-accent hover:underline font-medium">349 6709962</a>
                  <p class="text-sm text-muted-foreground mt-1">Lun - Ven: 9:00 - 13:00, 16:00 - 19:30</p>
                </div>
              </div>
            </CardContent>
          </Card>

          <!-- WhatsApp -->
          <Card class="shadow-sm hover:shadow-md transition-shadow">
            <CardContent class="pt-6 pb-6">
              <div class="flex items-start gap-4">
                <div class="w-11 h-11 rounded-lg bg-green-50 flex items-center justify-center flex-shrink-0">
                  <MessageCircle class="w-5 h-5 text-green-600" />
                </div>
                <div>
                  <h3 class="font-semibold text-foreground mb-1">WhatsApp</h3>
                  <a
                    href="https://wa.me/393496709962"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="text-green-600 hover:underline font-medium"
                  >
                    349 6709962
                  </a>
                  <p class="text-sm text-muted-foreground mt-1">Scrivici su WhatsApp per una risposta veloce</p>
                </div>
              </div>
            </CardContent>
          </Card>

          <!-- Email -->
          <Card class="shadow-sm hover:shadow-md transition-shadow">
            <CardContent class="pt-6 pb-6">
              <div class="flex items-start gap-4">
                <div class="w-11 h-11 rounded-lg bg-primary/5 flex items-center justify-center flex-shrink-0">
                  <Mail class="w-5 h-5 text-primary" />
                </div>
                <div>
                  <h3 class="font-semibold text-foreground mb-1">Email</h3>
                  <a href="mailto:Sgmsasbrindisi@gmail.com" class="text-accent hover:underline font-medium text-sm break-all">
                    Sgmsasbrindisi@gmail.com
                  </a>
                  <p class="text-sm text-muted-foreground mt-1">Rispondiamo entro 24 ore lavorative</p>
                </div>
              </div>
            </CardContent>
          </Card>

          <!-- Address -->
          <Card class="shadow-sm hover:shadow-md transition-shadow">
            <CardContent class="pt-6 pb-6">
              <div class="flex items-start gap-4">
                <div class="w-11 h-11 rounded-lg bg-primary/5 flex items-center justify-center flex-shrink-0">
                  <MapPin class="w-5 h-5 text-primary" />
                </div>
                <div>
                  <h3 class="font-semibold text-foreground mb-1">Sede</h3>
                  <p class="text-sm text-foreground">Via Romagna, 53</p>
                  <p class="text-sm text-foreground">72100 Brindisi (BR)</p>
                  <a
                    href="https://maps.google.com/?q=Via+Romagna+53+72100+Brindisi+BR"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="inline-flex items-center text-sm text-accent hover:underline mt-2"
                  >
                    Apri in Google Maps
                    <svg class="w-3.5 h-3.5 ml-1" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                      <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 6H5.25A2.25 2.25 0 0 0 3 8.25v10.5A2.25 2.25 0 0 0 5.25 21h10.5A2.25 2.25 0 0 0 18 18.75V10.5m-10.5 6L21 3m0 0h-5.25M21 3v5.25" />
                    </svg>
                  </a>
                </div>
              </div>
            </CardContent>
          </Card>
        </div>
      </div>
    </div>
  </section>
</template>
