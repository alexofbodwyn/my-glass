<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const props = defineProps({
  images: {
    type: Array,
    required: true,
  },
});

const activeIndex = ref(null);

const open = (i) => (activeIndex.value = i);
const close = () => (activeIndex.value = null);
const next = () =>
  (activeIndex.value = (activeIndex.value + 1) % props.images.length);
const prev = () =>
  (activeIndex.value =
    (activeIndex.value - 1 + props.images.length) % props.images.length);

const onKey = (e) => {
  if (activeIndex.value === null) return;
  if (e.key === "Escape") close();
  if (e.key === "ArrowRight") next();
  if (e.key === "ArrowLeft") prev();
};

onMounted(() => window.addEventListener("keydown", onKey));
onUnmounted(() => window.removeEventListener("keydown", onKey));
</script>

<template>
  <!-- Grid -->
  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
    <div
      v-for="(image, index) in images"
      :key="index"
      @click="open(index)"
      class="relative cursor-pointer overflow-hidden rounded-2xl bg-gray-100 group"
    >
      <div
        class="aspect-[4/3] bg-cover bg-center transition-transform duration-700 group-hover:scale-105"
        :style="{ backgroundImage: `url(${image.src})` }"
      />

      <div
        class="absolute inset-0 bg-black/0 group-hover:bg-black/20 transition"
      />

      <div
        class="absolute inset-x-0 bottom-0 p-4 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition"
      >
        <p class="text-white text-sm font-medium">
          {{ image.label }}
        </p>
      </div>
    </div>
  </div>

  <!-- Lightbox -->
  <transition name="overlay">
    <div
      v-if="activeIndex !== null"
      class="fixed inset-0 z-[9999] bg-black/95 flex items-center justify-center"
      @click.self="close"
    >
      <transition name="image">
        <div
          class="relative w-full h-full flex items-center justify-center px-6"
        >
          <!-- Image -->
          <div class="relative max-w-6xl w-full pointer-events-none">
            <img
              :src="images[activeIndex].src"
              :alt="images[activeIndex].label"
              class="w-full max-h-[80vh] object-contain rounded-lg mx-auto"
            />

            <div class="mt-4 text-center text-gray-300 text-sm">
              {{ images[activeIndex].label }}
              <span class="text-gray-500 ml-2">
                ({{ activeIndex + 1 }} / {{ images.length }})
              </span>
            </div>
          </div>

          <!-- Close -->
          <button
            @click="close"
            aria-label="Close gallery"
            class="absolute top-6 right-6 w-11 h-11 flex items-center justify-center rounded-full bg-white/10 hover:bg-white/20 text-white backdrop-blur pointer-events-auto"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              class="w-6 h-6"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>

          <!-- Prev -->
          <button
            @click.stop="prev"
            aria-label="Previous image"
            class="absolute left-4 top-1/2 -translate-y-1/2 w-12 h-12 flex items-center justify-center rounded-full bg-white/10 hover:bg-white/20 text-white backdrop-blur pointer-events-auto"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2.5"
              class="w-6 h-6"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M15.75 19.5L8.25 12l7.5-7.5"
              />
            </svg>
          </button>

          <!-- Next -->
          <button
            @click.stop="next"
            aria-label="Next image"
            class="absolute right-4 top-1/2 -translate-y-1/2 w-12 h-12 flex items-center justify-center rounded-full bg-white/10 hover:bg-white/20 text-white backdrop-blur pointer-events-auto"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2.5"
              class="w-6 h-6"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M8.25 4.5l7.5 7.5-7.5 7.5"
              />
            </svg>
          </button>

          <!-- Hint -->
          <div
            class="hidden md:block absolute bottom-6 left-1/2 -translate-x-1/2 text-gray-500 text-xs pointer-events-none"
          >
            Use ← → keys • ESC to close
          </div>
        </div>
      </transition>
    </div>
  </transition>
</template>

<style scoped>
.overlay-enter-active,
.overlay-leave-active {
  transition: opacity 0.25s ease;
}
.overlay-enter-from,
.overlay-leave-to {
  opacity: 0;
}

.image-enter-active {
  transition:
    opacity 0.3s ease,
    transform 0.3s ease;
}
.image-enter-from {
  opacity: 0;
  transform: scale(0.96);
}
</style>
