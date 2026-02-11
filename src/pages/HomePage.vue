<script setup>
import { ref } from "vue";

const mobileMenuOpen = ref(false);
</script>

<template>
  <div class="min-h-screen bg-white text-black flex flex-col">
    <header class="relative inset-x-0 top-0 z-20 bg-white/70 backdrop-blur border-b border-black/5">
      <div class="mx-auto flex h-16 max-w-6xl items-center justify-between px-4 sm:px-6">
        <RouterLink to="/" class="font-['Passion_One'] text-xl tracking-wide sm:text-2xl">David Kutlesa</RouterLink>
        <nav class="hidden items-center gap-8 text-sm font-medium md:flex">
          <RouterLink to="/" class="hover:text-gray-500 transition underline">Home</RouterLink>
          <RouterLink to="/about" class="hover:text-gray-500 transition">Über mich</RouterLink>
          <RouterLink to="/school" class="hover:text-gray-500 transition">Schule</RouterLink>
          <RouterLink to="/projects" class="hover:text-gray-500 transition">Projekte</RouterLink>
          <RouterLink to="/contact" class="hover:text-gray-500 transition">Kontakt</RouterLink>
        </nav>
        <RouterLink
          to="/contact"
          class="hidden rounded-full border border-black/10 px-4 py-2 text-xs font-semibold uppercase tracking-widest hover:border-black/30 transition md:inline-flex"
        >
          Let’s Talk
        </RouterLink>
        <button
          type="button"
          class="flex h-10 w-10 items-center justify-center rounded-md border border-black/15 md:hidden"
          @click="mobileMenuOpen = !mobileMenuOpen"
          aria-label="Menü öffnen"
        >
          <svg class="h-5 w-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M4 6h16M4 12h16M4 18h16" />
          </svg>
        </button>
      </div>
      <nav v-if="mobileMenuOpen" class="border-t border-black/10 bg-white md:hidden">
        <div class="mx-auto flex max-w-6xl flex-col px-4 py-4 text-sm font-medium">
          <RouterLink to="/" class="py-2" @click="mobileMenuOpen = false">Home</RouterLink>
          <RouterLink to="/about" class="py-2" @click="mobileMenuOpen = false">Über mich</RouterLink>
          <RouterLink to="/school" class="py-2" @click="mobileMenuOpen = false">Schule</RouterLink>
          <RouterLink to="/projects" class="py-2" @click="mobileMenuOpen = false">Projekte</RouterLink>
          <RouterLink to="/contact" class="py-2" @click="mobileMenuOpen = false">Kontakt</RouterLink>
        </div>
      </nav>
    </header>

    <main class="pt-20 flex-1">
      <section class="relative min-h-[calc(100vh-5rem)]">
        <div class="mx-auto max-w-6xl px-4 sm:px-6 pt-8 sm:pt-12">
          <p class="text-xs uppercase tracking-[0.3em] text-black/60 sm:text-sm">Portfolio 2026</p>
          <h1 class="mt-3 text-[clamp(30px,8vw,72px)] leading-[1]">
            <span class="font-['Lato'] font-black uppercase tracking-[0.14em] sm:tracking-[0.18em]">Fullstack Developer</span>
            <span class="block font-['Gravitas_One'] text-black/55">fokussiert & strukturiert</span>
          </h1>
          <p class="mt-6 max-w-2xl text-[15px] leading-7 text-black/65">
            Ich bin Applikationsentwickler im ersten Lehrjahr bei Swisscom.
            Ich interessiere mich für Programmieren und IT.
            Offen für neue Erfahrungen.
          </p>

          <div class="mt-8 flex flex-wrap items-center gap-4 sm:mt-10">
            <RouterLink to="/projects" class="rounded-full bg-black px-6 py-3 text-sm text-white hover:bg-black/80 transition">
              Projekte ansehen
            </RouterLink>
            <RouterLink to="/contact" class="rounded-full border border-black/20 px-6 py-3 text-sm hover:border-black/40 transition">
              Kontakt
            </RouterLink>
          </div>
          <div class="mt-6 grid w-full max-w-5xl grid-cols-1 gap-4 sm:grid-cols-3">
            <div class="rounded-2xl border border-black/10 bg-white px-4 py-4">
              <p class="text-xs uppercase tracking-[0.2em] text-black/50">Lehrjahr</p>
              <p class="mt-2 text-lg font-semibold">1. Jahr</p>
            </div>
            <div class="rounded-2xl border border-black/10 bg-white px-4 py-4">
              <p class="text-xs uppercase tracking-[0.2em] text-black/50">Fokus</p>
              <p class="mt-2 text-lg font-semibold">Web Skills</p>
            </div>
            <div class="rounded-2xl border border-black/10 bg-white px-4 py-4">
              <p class="text-xs uppercase tracking-[0.2em] text-black/50">Projekte</p>
              <p class="mt-2 text-lg font-semibold">Portfolio & Apps</p>
            </div>
          </div>
        </div>
      </section>

      <section class="w-full bg-gray-50 py-14 sm:py-20">
        <div class="mx-auto grid max-w-6xl items-center gap-8 px-4 sm:px-6 lg:grid-cols-[1fr_380px] lg:gap-12">
          <div>
            <h2 class="font-['Gravitas_One'] text-4xl sm:text-5xl">David Kutlesa</h2>
            <p class="mt-4 max-w-2xl text-[15px] leading-7 tracking-wide text-black/65">
              Ich bin Applikationsentwickler im ersten Lehrjahr bei Swisscom.
              Ich interessiere mich für Programmieren und IT.
              Offen für neue Erfahrungen.
            </p>
            <RouterLink
              to="/about"
              class="inline-block mt-8 rounded-full bg-black px-8 py-3 text-sm text-white hover:bg-black/80 transition sm:px-12"
            >
              Mehr über mich erfahren?
            </RouterLink>
          </div>
          <img
            class="mx-auto w-full max-w-[380px] rounded-3xl object-cover shadow-sm lg:mx-0 lg:justify-self-end"
            src="./Photos/_A7_1342.jpg"
            alt="David Kutlesa"
          />
        </div>

        <video
          class="mx-auto mt-10 w-[92%] max-w-3xl rounded-3xl object-cover"
          autoplay
          loop
          muted
          playsinline
        >
          <source src="/src/pages/videos/copy_42F842B5-2639-4FC3-9870-E3A74AB4F6D4.mp4" type="video/mp4" />
        </video>
      </section>
    </main>

    <footer class="w-full border-t border-gray-200">
      <div class="mx-auto flex max-w-6xl flex-col items-start justify-between gap-3 px-4 py-6 sm:flex-row sm:items-center sm:px-6">
        <p class="text-sm text-gray-500">© 2026 David Kutlesa</p>
        <div class="flex gap-4 text-sm text-gray-500">
          <a href="#" class="hover:text-black">Impressum</a>
          <a href="#" class="hover:text-black">Kontakt</a>
          <a href="#" class="hover:text-black">GitHub</a>
        </div>
      </div>
    </footer>
  </div>
</template>

