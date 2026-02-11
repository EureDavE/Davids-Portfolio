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
          <RouterLink to="/school" class="hover:text-gray-500 transition underline">Schule</RouterLink>
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

    <main class="mx-auto max-w-6xl px-6 pb-16 pt-28">
      <section class="grid gap-8 lg:grid-cols-[1.2fr_0.8fr] lg:items-end">
        <div>
          <p class="text-xs uppercase tracking-[0.25em] text-black/50">Schule</p>
          <h1 class="mt-3 text-[clamp(34px,5vw,64px)] leading-[1.03]">
            <span class="font-['Lato'] font-black uppercase tracking-[0.12em]">Lernen mit Energie</span>
            <span class="block font-['Gravitas_One'] text-black/55">zwischen Schule und Winterthur</span>
          </h1>
          <p class="mt-6 max-w-2xl text-[15px] leading-7 text-black/70">
            Ich bin im ersten Lehrjahr als Applikationsentwickler und gehe jeden Montag und Dienstag in die Schule.
            Dort habe ich viel Spass, lerne Neues und kann mich laufend verbessern.
          </p>
        </div>

        <div class="rounded-3xl border border-black/10 bg-gradient-to-br from-slate-50 via-white to-zinc-100 p-6 shadow-sm">
          <p class="text-xs uppercase tracking-[0.2em] text-black/50">Wochenrhythmus</p>
          <p class="mt-4 text-2xl font-semibold">Montag + Dienstag</p>
          <p class="mt-2 text-sm leading-6 text-black/70">
            Schultage mit Fokus auf Informatik, Teamarbeit und praktische Aufgaben.
          </p>
        </div>
      </section>

      <section class="mt-10 grid gap-4 sm:grid-cols-2 lg:grid-cols-3">
        <article class="rounded-2xl border border-black/10 bg-white p-5">
          <p class="text-xs uppercase tracking-[0.2em] text-black/45">Schule</p>
          <h2 class="mt-2 text-lg font-semibold">Zwei feste Tage</h2>
          <p class="mt-2 text-sm leading-6 text-black/70">
            Montag und Dienstag sind meine Schultage. Ich nutze diese Zeit, um mein Fachwissen zu vertiefen.
          </p>
        </article>

        <article class="rounded-2xl border border-black/10 bg-white p-5">
          <p class="text-xs uppercase tracking-[0.2em] text-black/45">Motivation</p>
          <h2 class="mt-2 text-lg font-semibold">Lernen macht Spass</h2>
          <p class="mt-2 text-sm leading-6 text-black/70">
            Mir macht die Arbeit mit Code Spass. Besonders cool ist es, wenn aus einer Idee ein funktionierendes Projekt wird.
          </p>
        </article>

        <article class="rounded-2xl border border-black/10 bg-white p-5 sm:col-span-2 lg:col-span-1">
          <p class="text-xs uppercase tracking-[0.2em] text-black/45">Lernen</p>
          <h2 class="mt-2 text-lg font-semibold">Lernphase</h2>
          <p class="mt-2 text-sm leading-6 text-black/70">
            Ich gehe mit Freunden ein bis zweimal pro Woche in die Bibliothek, und wir unterstützen uns gegenseitig.
          </p>
        </article>
      </section>
    </main>
  </div>
</template>
