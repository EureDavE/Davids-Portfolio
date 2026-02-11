<script setup>
// This Comment is because of Repo Change
import { reactive, ref } from "vue";

const contactEmail = "david.kutlesa@swisscom.com";

const form = reactive({
  name: "",
  email: "",
  message: "",
});
const mobileMenuOpen = ref(false);

const sendMessage = () => {
  const subject = `Kontaktanfrage von ${form.name}`;
  const body = `Name: ${form.name}%0AEmail: ${form.email}%0A%0ANachricht:%0A${form.message}`;
  window.location.href = `mailto:${contactEmail}?subject=${encodeURIComponent(subject)}&body=${body}`;
};
</script>

<template>
  <div class="min-h-screen bg-white text-black">
    <header class="fixed inset-x-0 top-0 z-20 bg-white/70 backdrop-blur border-b border-black/5">
      <div class="mx-auto flex h-16 max-w-6xl items-center justify-between px-4 sm:px-6">
        <RouterLink to="/" class="font-['Passion_One'] text-xl tracking-wide sm:text-2xl">David Kutlesa</RouterLink>
        <nav class="hidden items-center gap-8 text-sm font-medium md:flex">
          <RouterLink to="/" class="hover:text-gray-500 transition">Home</RouterLink>
          <RouterLink to="/about" class="hover:text-gray-500 transition">Über mich</RouterLink>
          <RouterLink to="/school" class="hover:text-gray-500 transition">Schule</RouterLink>
          <RouterLink to="/projects" class="hover:text-gray-500 transition">Projekte</RouterLink>
          <RouterLink to="/contact" class="hover:text-gray-500 transition underline">Kontakt</RouterLink>
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
      <section class="grid gap-10 lg:grid-cols-[1fr_1fr] lg:items-start">
        <div>
          <p class="text-xs uppercase tracking-[0.24em] text-black/50">Kontakt</p>
          <h1 class="mt-3 text-[clamp(34px,5vw,62px)] leading-[1.03]">
            <span class="font-['Gravitas_One']">Lass uns sprechen</span>
          </h1>
          <p class="mt-5 max-w-xl text-sm leading-7 text-black/70">
            Du kannst mich direkt per E-Mail oder über Social Media erreichen.
            Ich antworte so schnell wie möglich.
          </p>

          <div class="mt-8 grid gap-3 sm:grid-cols-2">
            <a
              :href="`mailto:${contactEmail}`"
              class="rounded-2xl border border-black/10 p-4 transition hover:border-black/30"
            >
              <p class="text-xs uppercase tracking-[0.2em] text-black/45">E-Mail</p>
              <p class="mt-2 text-sm font-medium">{{ contactEmail }}</p>
            </a>

            <div class="rounded-2xl border border-black/10 p-4">
              <p class="text-xs uppercase tracking-[0.2em] text-black/45">Telefon</p>
              <p class="mt-2 text-sm font-medium">Auf Anfrage per E-Mail</p>
            </div>

            <div class="rounded-2xl border border-black/10 p-4">
              <p class="text-xs uppercase tracking-[0.2em] text-black/45">Standort</p>
              <p class="mt-2 text-sm font-medium">Kanton Zürich, Schweiz</p>
            </div>

            <div class="rounded-2xl border border-black/10 p-4">
              <p class="text-xs uppercase tracking-[0.2em] text-black/45">Verfügbarkeit</p>
              <p class="mt-2 text-sm font-medium">Mittwoch - Freitag</p>
            </div>
          </div>

          <div class="mt-6 flex flex-wrap gap-3">
            <a
              href="https://github.com/EureDavE"
              target="_blank"
              rel="noreferrer"
              class="rounded-full border border-black/15 px-4 py-2 text-sm transition hover:border-black/35"
            >
              GitHub
            </a>
            <a
              href="https://www.linkedin.com/in/david-kutlesa-a31212397"
              target="_blank"
              rel="noreferrer"
              class="rounded-full border border-black/15 px-4 py-2 text-sm transition hover:border-black/35"
            >
              LinkedIn
            </a>
          </div>
        </div>

        <section class="rounded-3xl border border-black/10 bg-gradient-to-b from-slate-50 to-white p-6 sm:p-8">
          <p class="text-xs uppercase tracking-[0.2em] text-black/50">Nachricht senden</p>
          <form class="mt-5 space-y-4" @submit.prevent="sendMessage">
            <div>
              <label for="name" class="text-xs uppercase tracking-[0.2em] text-black/45">Name</label>
              <input
                id="name"
                type="text"
                placeholder="Dein Name"
                v-model="form.name"
                required
                class="mt-2 w-full rounded-xl border border-black/15 bg-white px-4 py-3 text-sm outline-none transition focus:border-black/35"
              />
            </div>

            <div>
              <label for="email" class="text-xs uppercase tracking-[0.2em] text-black/45">E-Mail</label>
              <input
                id="email"
                type="email"
                placeholder="deine.email@beispiel.ch"
                v-model="form.email"
                required
                class="mt-2 w-full rounded-xl border border-black/15 bg-white px-4 py-3 text-sm outline-none transition focus:border-black/35"
              />
            </div>

            <div>
              <label for="message" class="text-xs uppercase tracking-[0.2em] text-black/45">Nachricht</label>
              <textarea
                id="message"
                rows="5"
                placeholder="Schreib mir deine Nachricht..."
                v-model="form.message"
                required
                class="mt-2 w-full rounded-xl border border-black/15 bg-white px-4 py-3 text-sm outline-none transition focus:border-black/35"
              ></textarea>
            </div>

            <button
              type="submit"
              class="w-full rounded-full bg-black px-6 py-3 text-sm font-medium text-white transition hover:bg-black/85"
            >
              Nachricht senden
            </button>
          </form>
        </section>
      </section>
    </main>
  </div>
</template>
