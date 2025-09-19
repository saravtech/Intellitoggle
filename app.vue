<script setup>
</script>

<template>
  <NuxtPage />
</template>

<style>
@tailwind base;
@tailwind components;
@tailwind utilities;
@layer base {
  html, body {
    @apply font-brand antialiased text-[15px] md:text-[16px] leading-[1.6] text-white;
  }

  /* Headings used across the site */
  h1 { @apply font-extrabold tracking-tightish leading-[1.05]; }
  h2 { @apply font-bold tracking-tightish leading-[1.15]; }
  h3 { @apply font-semibold leading-tight; }
}
</style>
