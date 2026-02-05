<script setup lang="ts">
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import TrustBar from './components/TrustBar.vue'
import ServicesSection from './components/ServicesSection.vue'
import AboutSection from './components/AboutSection.vue'
import WhyUsSection from './components/WhyUsSection.vue'
import ProductsShowcase from './components/ProductsShowcase.vue'
import CtaBanner from './components/CtaBanner.vue'
import ContactSection from './components/ContactSection.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<template>
  <div class="min-h-screen bg-background">
    <NavBar />
    <main>
      <HeroSection />
      <TrustBar />
      <ServicesSection />
      <AboutSection />
      <WhyUsSection />
      <ProductsShowcase />
      <CtaBanner />
      <ContactSection />
    </main>
    <FooterSection />
  </div>
</template>
