<script setup>
import { computed, ref } from "vue";
import heroPhoto from "./Photos/_A7_1342.jpg";
const photos = Object.entries(
  import.meta.glob("./Carussel/*.{jpg,jpeg,png,webp,avif,JPG,JPEG,PNG,WEBP,AVIF}", {
    eager: true,
    import: "default",
  }),
)
  .sort(([a], [b]) => a.localeCompare(b, undefined, { numeric: true, sensitivity: "base" }))
  .map(([_, src], index) => ({
    src,
    alt: `David Portrait ${index + 1}`,
  }));

const currentIndex = ref(0);
const mobileMenuOpen = ref(false);
const currentPhoto = computed(() => photos[currentIndex.value] ?? { src: "", alt: "Foto" });

const prevPhoto = () => {
  if (photos.length < 2) return;
  currentIndex.value = (currentIndex.value - 1 + photos.length) % photos.length;
};

const nextPhoto = () => {
  if (photos.length < 2) return;
  currentIndex.value = (currentIndex.value + 1) % photos.length;
};
</script>

<template>
  <div class="min-h-screen bg-white text-black">
    <header class="fixed inset-x-0 top-0 z-20 bg-white/70 backdrop-blur border-b border-black/5">
      <div class="mx-auto flex h-16 max-w-6xl items-center justify-between px-4 sm:px-6">
        <RouterLink to="/" class="font-['Passion_One'] text-xl tracking-wide sm:text-2xl">David Kutlesa</RouterLink>
        <nav class="hidden items-center gap-8 text-sm font-medium md:flex">
          <RouterLink to="/" class="hover:text-gray-500 transition">Home</RouterLink>
          <RouterLink to="/about" class="hover:text-gray-500 transition underline">Über mich</RouterLink>
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

    <main class="mx-auto max-w-6xl px-6 pb-20 pt-28">
      <section class="grid gap-8 lg:grid-cols-[1.2fr_0.8fr] lg:items-center">
        <div>
          <p class="text-xs uppercase tracking-[0.24em] text-black/50">über mich</p>
          <h1 class="mt-3 text-[clamp(34px,5vw,66px)] leading-[1.02]">
            <span class="font-['Gravitas_One']">Hey There!</span>
            <span class="mt-2 block font-['Lato'] font-black uppercase tracking-[0.12em]">I'm David</span>
          </h1>
          <p class="mt-6 text-[15px] leading-7 text-black/70">
            Ich bin 16, wohne im Kanton Zürich und bin Lernender im
            1. Lehrjahr bei Swisscom.
          </p>
        </div>

        <div class="h-[320px] overflow-hidden rounded-3xl border border-black/10 bg-zinc-100 sm:h-[420px]">
          <img :src="heroPhoto" alt="Foto von David" class="h-full w-full object-cover object-top" />
        </div>
      </section>

      <section class="mt-10 grid gap-4 sm:grid-cols-2">
        <article class="rounded-2xl border border-black/10 p-5">
          <p class="text-xs uppercase tracking-[0.2em] text-black/45">Hobbys</p>
          <p class="mt-2 text-sm leading-7 text-black/75">
            Programmieren, Musik und Billard geben mir Energie.
            Genauso wichtig ist mir Zeit mit Freunden und Familie.
          </p>
        </article>
        <article class="rounded-2xl border border-black/10 p-5">
          <p class="text-xs uppercase tracking-[0.2em] text-black/45">Familie</p>
          <p class="mt-2 text-sm leading-7 text-black/75">
            Ich habe einen älteren Bruder, der 8 Jahre älter ist als ich.
            Von ihm habe ich gelernt, dranzubleiben und Verantwortung zu übernehmen.
            Meine Familie unterstützt meinen Weg in der Informatik jeden Tag.
          </p>
        </article>
      </section>

      <section class="mt-12 rounded-3xl border border-black/10 bg-gradient-to-b from-slate-50 to-white p-6 sm:p-8">
        <p class="text-xs uppercase tracking-[0.2em] text-black/50">Warum dieser Beruf</p>
        <p class="mt-4 text-sm leading-7 text-black/75">
          Schon als Kind war ich von Technik begeistert. Seit meinem
          13. Lebensjahr beschäftige ich mich damit, wie Systeme funktionieren
          und wie man technische Probleme lösungsorientiert angeht.
        </p>
        <p class="mt-4 text-sm leading-7 text-black/75">
          Durch meinen Onkel kam ich zum Programmieren. Mit meinem ersten
          HTML-Projekt öffnete sich für mich eine ganz neue Welt.
        </p>
        <p class="mt-4 text-sm leading-7 text-black/75">
          Heute bin ich Lernender im 1. Lehrjahr bei Swisscom und arbeite jeden Tag daran,
          mich fachlich und persönlich weiterzuentwickeln.
        </p>
      </section>

      <section class="mt-12">
        <div class="flex items-end justify-between gap-4">
          <div>
            <p class="text-xs uppercase tracking-[0.2em] text-black/50">Fotos</p>
            <h2 class="mt-2 font-['Gravitas_One'] text-3xl">Karussell</h2>
          </div>
          <div class="flex gap-2">
            <button
              type="button"
              class="rounded-full border border-black/15 px-4 py-2 text-sm hover:border-black/35 transition"
              @click="prevPhoto"
            >
              Zurück
            </button>
            <button
              type="button"
              class="rounded-full border border-black/15 px-4 py-2 text-sm hover:border-black/35 transition"
              @click="nextPhoto"
            >
              Weiter
            </button>
          </div>
        </div>

        <div class="mt-5 overflow-hidden rounded-3xl border text-center justify-center border-black/10 bg-zinc-100">
          <img :src="currentPhoto.src" :alt="currentPhoto.alt" class="h-[420px] w-full object-contain" />
        </div>

        <div class="mt-4 flex flex-wrap gap-2">
          <button
            v-for="(_, index) in photos"
            :key="index"
            type="button"
            class="h-2.5 w-8 rounded-full transition"
            :class="index === currentIndex ? 'bg-black' : 'bg-black/20 hover:bg-black/35'"
            @click="currentIndex = index"
          ></button>
        </div>
      </section>
    </main>
  </div>
</template>
