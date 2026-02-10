<template>
  <div class="min-h-screen bg-white text-black">
    <header class="fixed inset-x-0 top-0 z-20 bg-white/70 backdrop-blur border-b border-black/5">
      <div class="mx-auto flex h-16 max-w-6xl items-center justify-between px-6">
        <RouterLink to="/" class="font-['Passion_One'] text-2xl tracking-wide">David Kutlesa</RouterLink>
        <nav class="hidden items-center gap-8 text-sm font-medium md:flex">
          <RouterLink to="/" class="hover:text-gray-500 transition">Home</RouterLink>
          <RouterLink to="/about" class="hover:text-gray-500 transition">Über mich</RouterLink>
          <RouterLink to="/school" class="hover:text-gray-500 transition">Schule & Kurse</RouterLink>
          <RouterLink to="/projects" class="hover:text-gray-500 transition">Projekte</RouterLink>
          <RouterLink to="/contact" class="hover:text-gray-500 transition">Kontakt</RouterLink>
        </nav>
        <RouterLink
          to="/contact"
          class="rounded-full border border-black/10 px-4 py-2 text-xs font-semibold uppercase tracking-widest hover:border-black/30 transition"
        >
          Let’s Talk
        </RouterLink>
      </div>
    </header>

    <main class="pt-28">
      <section class="relative">
        <div class="mx-auto max-w-6xl px-6">
          <p class="text-sm uppercase tracking-[0.3em] text-black/60">Portfolio 2026</p>
          <h1 class="mt-5 text-[clamp(34px,5.2vw,72px)] leading-[1]">
            <span class="font-['Lato'] font-black uppercase tracking-[0.18em]">Frontend Developer</span>
            <span class="block font-['Gravitas_One'] text-black/55">mit Fokus auf klare Interfaces</span>
          </h1>
          <p class="mt-6 max-w-2xl text-[15px] leading-7 text-black/65">
            Ich baue ruhige, präzise Web-Interfaces mit Fokus auf Typografie, Bewegung und Struktur.
            Offen für Projekte, Praktika und Kooperationen.
          </p>
          <div class="mt-8 flex flex-wrap items-center gap-4">
            <RouterLink to="/projects" class="rounded-full bg-black px-6 py-3 text-sm text-white hover:bg-black/80 transition">
              Projekte ansehen
            </RouterLink>
            <RouterLink to="/contact" class="rounded-full border border-black/20 px-6 py-3 text-sm hover:border-black/40 transition">
              Kontakt
            </RouterLink>
          </div>
        </div>

        <div class="mt-16 w-full text-2xl overflow-hidden py-6" aria-label="David Kutlesa Portfolio">
          <div class="flex w-max animate-marquee">
            <div class="shrink-0 font-['Passion_One'] text-[clamp(56px,10vw,140px)] leading-[0.95] tracking-[0.015em] whitespace-nowrap pr-16">
              David Kutlesa Portfolio David Kutlesa Portfolio David Kutlesa Portfolio
            </div>
            <div class="shrink-0 font-['Passion_One'] text-[clamp(56px,10vw,140px)] leading-[0.95] tracking-[0.015em] whitespace-nowrap pr-16">
              David Kutlesa Portfolio David Kutlesa Portfolio David Kutlesa Portfolio
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>
