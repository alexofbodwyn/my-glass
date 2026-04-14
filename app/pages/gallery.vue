<script setup>
const images = [
  {
    src: "https://images.unsplash.com/photo-1600585154340-be6161a56a0c?q=80&w=1800&auto=format&fit=crop",
    label: "Slimline aluminium glazing",
  },
  {
    src: "https://images.unsplash.com/photo-1618220179428-22790b461013?q=80&w=1800&auto=format&fit=crop",
    label: "Contemporary residential project",
  },
  {
    src: "https://images.unsplash.com/photo-1597047084897-51e81819a499?q=80&w=1800&auto=format&fit=crop",
    label: "Minimal aluminium doors",
  },
  {
    src: "https://images.unsplash.com/photo-1600566753151-384129cf4e3e?q=80&w=1800&auto=format&fit=crop",
    label: "Architectural glazing detail",
  },
  {
    src: "https://images.unsplash.com/photo-1600607687939-ce8a6c25118c?q=80&w=1800&auto=format&fit=crop",
    label: "Modern extension installation",
  },
];
</script>

<template>
  <section class="bg-white py-60">
    <div class="container mx-auto px-4">
      <!-- Header -->
      <div class="mb-16">
        <div
          class="text-lg uppercase tracking-widest text-[#3ea8db] font-medium mb-3"
        >
          Gallery
        </div>

        <h1 class="text-4xl md:text-5xl font-light text-gray-900 leading-tight">
          Recent <strong>Projects</strong><br />
          & Installed Systems
        </h1>

        <p class="mt-6 text-gray-600 leading-relaxed max-w-2xl">
          A selection of aluminium doors, glazing, and architectural
          installations completed for homes and commercial spaces.
        </p>
      </div>

      <!-- Reusable gallery -->
      <GalleryLightbox :images="images" />
    </div>
  </section>
</template>
