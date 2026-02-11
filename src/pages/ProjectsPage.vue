<script setup>
import { ref } from "vue";

const mobileMenuOpen = ref(false);
</script>

<template>
  <div class="min-h-screen bg-white text-black">
    <header class="fixed inset-x-0 top-0 z-20 bg-white/70 backdrop-blur border-b border-black/5">
      <div class="mx-auto flex h-16 max-w-6xl items-center justify-between px-4 sm:px-6">
        <RouterLink to="/" class="font-['Passion_One'] text-xl tracking-wide sm:text-2xl">David Kutlesa</RouterLink>
        <nav class="hidden items-center gap-8 text-sm font-medium md:flex">
          <RouterLink to="/" class="hover:text-gray-500 transition">Home</RouterLink>
          <RouterLink to="/about" class="hover:text-gray-500 transition">Über mich</RouterLink>
          <RouterLink to="/school" class="hover:text-gray-500 transition ">Schule</RouterLink>
          <RouterLink to="/projects" class="hover:text-gray-500 transition underline">Projekte</RouterLink>
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

    <main class="mx-auto max-w-5xl px-6 pt-24 pb-16">
      <h1 class="font-['Gravitas_One'] text-4xl text-center">Projekte</h1>
     

      <section class="mt-10">
        <div class="relative">
          <span class="absolute bottom-0 left-2 top-0 w-[2px] bg-black/20 md:left-1/2 md:-translate-x-1/2"></span>

          <article class="relative mb-8 ml-8 border border-black/15 bg-white p-5 shadow-sm md:ml-0 md:w-[calc(50%-1.5rem)]">
            <span class="absolute -left-[31px] top-6 h-4 w-4 border border-black bg-white md:-right-8 md:left-auto"></span>
            <p class="text-xs uppercase tracking-[0.2em] text-black/50">Jahr 1</p>
            <h2 class="mt-2 text-xl font-semibold">Team Minion</h2>
            <p class="mt-2 text-sm text-green-500">Status: Abgeschlossen</p>
            <p class="mt-2 text-sm leading-6 text-black/70">
              Beschreibung: Wir hatten die Möglichkeit, unsere eigene Portfolio-Seite zu erstellen. Im Team Minion konnte ich meine Fachkenntnisse in HTML, CSS, JavaScript und Angular vertiefen.
            </p>
          </article>

          <article class="relative mb-8 ml-8 border border-black/15 bg-white p-5 shadow-sm md:ml-auto md:w-[calc(50%-1.5rem)]">
            <span class="absolute -left-[31px] top-6 h-4 w-4 border border-black bg-white md:-left-8"></span>
            <p class="text-xs uppercase tracking-[0.2em] text-black/50">Jahr 1</p>
            <h2 class="mt-2 text-xl font-semibold">Sitelab</h2>
            <p class="mt-2 text-sm text-blue-500">Status: In Bearbeitung</p>
            <p class="mt-2 text-sm leading-6 text-black/70">
              Beschreibung: Bei Sitelab lernst du vor allem mit JavaScript und TypeScript zu programmieren.
Du nutzt diese Sprachen für Frontend (zum Beispiel mit React oder Next.js) und Backend (mit Node.js oder NestJS) Entwicklung.
            </p>
          </article>

          <article class="relative mb-8 ml-8 border border-black/15 bg-white p-5 shadow-sm md:ml-0 md:w-[calc(50%-1.5rem)]">
            <span class="absolute -left-[31px] top-6 h-4 w-4 border border-black bg-white md:-right-8 md:left-auto"></span>
            <p class="text-xs uppercase tracking-[0.2em] text-black/50">Jahr 2</p>
            <h2 class="mt-2 text-xl font-semibold">Projekt 3</h2>
            <p class="mt-2 text-sm text-yellow-500">Status: Geplant</p>
            <p class="mt-2 text-sm leading-6 text-black/70">
              
            </p>
          </article>

          <article class="relative mb-8 ml-8 border border-black/15 bg-white p-5 shadow-sm md:ml-auto md:w-[calc(50%-1.5rem)]">
            <span class="absolute -left-[31px] top-6 h-4 w-4 border border-black bg-white md:-left-8"></span>
            <p class="text-xs uppercase tracking-[0.2em] text-black/50">Jahr 3</p>
            <h2 class="mt-2 text-xl font-semibold">Projekt 4</h2>
            <p class="mt-2 text-sm text-yellow-500">Status: Geplant</p>
            <p class="mt-2 text-sm leading-6 text-black/70">
             
            </p>
          </article>

          <article class="relative ml-8 border border-black/15 bg-white p-5 shadow-sm md:ml-0 md:w-[calc(50%-1.5rem)]">
            <span class="absolute -left-[31px] top-6 h-4 w-4 border border-black bg-white md:-right-8 md:left-auto"></span>
            <p class="text-xs uppercase tracking-[0.2em] text-black/50">Jahr 4</p>
            <h2 class="mt-2 text-xl font-semibold">Projekt 5</h2>
            <p class="mt-2 text-sm text-yellow-500">Status: Geplant</p>
            <p class="mt-2 text-sm leading-6 text-black/70">
              
            </p>
          </article>
        </div>
      </section>
    </main>
  </div>
</template>
