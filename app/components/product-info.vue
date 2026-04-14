<script setup lang="ts">
interface GalleryImage {
  src: string;
  label: string;
}
interface SpecRow {
  label: string;
  value: string;
}
defineProps<{
  pageTitle: string;
  pageIntro: string;
  heroImage: string;
  heroAlt: string;
  sectionTitle: string;
  paragraphs: string[];
  specsTitle: string;
  specs: SpecRow[];
  galleryTitle: string;
  galleryImages: GalleryImage[];
  ctaText: string;
  ctaHref: string;
}>();
</script>
<template>
  <div class="pt-50 pb-16">
    <div class="container mx-auto px-4">
      <!-- Header -->
      <div class="mb-16 md:mb-20 max-w-3xl">
        <h1
          class="text-3xl lg:text-5xl font-light tracking-wider text-gray-900 mb-4"
          v-html="pageTitle"
        />
        <p
          class="mt-6 text-gray-600 leading-relaxed text-sm lg:text-lg tracking-wide"
          v-html="pageIntro"
        ></p>
      </div>
      <!-- Main Grid -->
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:gap-16 mb-16">
        <div>
          <img
            :src="heroImage"
            :alt="heroAlt"
            class="w-full h-[400px] lg:h-[500px] object-cover rounded-sm shadow-lg"
          />
        </div>
        <div class="flex flex-col justify-center">
          <h2
            class="text-xl md:text-2xl font-light text-gray-900 mb-6 tracking-wide"
          >
            {{ sectionTitle }}
          </h2>
          <p
            v-for="(p, i) in paragraphs"
            :key="i"
            class="text-gray-600 leading-relaxed mb-6 text-sm md:text-base"
          >
            {{ p }}
          </p>
          <div class="bg-gray-50 rounded-sm p-6 md:p-8 mt-4">
            <h3 class="text-lg font-medium text-gray-900 mb-6">
              {{ specsTitle }}
            </h3>
            <div class="space-y-4">
              <div
                v-for="(row, i) in specs"
                :key="i"
                class="grid grid-cols-2 gap-4 pb-4 border-b last:border-b-0 border-gray-200"
              >
                <div class="text-gray-700 font-medium text-sm">
                  {{ row.label }}
                </div>
                <div class="text-gray-900 text-sm">
                  {{ row.value }}
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- Gallery -->
      <div class="mt-16 md:mt-20">
        <h2
          class="text-xl md:text-2xl font-light text-gray-900 mb-8 md:mb-12 tracking-wide"
        >
          {{ galleryTitle }}
        </h2>
        <GalleryLightbox :images="galleryImages" />
      </div>
      <!-- CTA -->
      <div class="mt-16 md:mt-20 text-center">
        <p class="text-sm lg:text-lg text-gray-600 mb-8 tracking-wide">
          {{ ctaText }}
        </p>
        <div class="flex justify-center">
          <cta-link :href="ctaHref">Request a Quote</cta-link>
        </div>
      </div>
    </div>
  </div>
</template>
