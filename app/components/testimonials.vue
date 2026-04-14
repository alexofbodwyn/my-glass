<script setup lang="ts">
import { ref, computed } from "vue";

/* ---------------- Testimonials Data ---------------- */

interface Testimonial {
  name: string;
  role: string;
  text: string;
  image: string;
}

const testimonials: Testimonial[] = [
  {
    name: "James Walker",
    role: "Homeowner",
    text: "Fantastic service from start to finish. The quality of the glass and the installation exceeded expectations.",
    image:
      "https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?q=80&w=100",
  },
  {
    name: "Sarah Mitchell",
    role: "Architect",
    text: "Clean detailing, precise fitting, and excellent communication throughout the project.",
    image:
      "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?q=80&w=100",
  },
  {
    name: "Daniel Roberts",
    role: "Property Developer",
    text: "Reliable, professional, and consistently high quality. We use My Glass on all our projects.",
    image:
      "https://images.unsplash.com/photo-1633332755192-727a05c4013d?q=80&w=100",
  },
];

/* ---------------- Carousel Logic ---------------- */

const index = ref(0);

const next = () => {
  index.value = (index.value + 1) % testimonials.length;
};

const prev = () => {
  index.value = index.value === 0 ? testimonials.length - 1 : index.value - 1;
};

const trackStyle = computed(() => ({
  transform: `translateX(-${index.value * 100}%)`,
}));
</script>

<template>
  <!-- ================= TESTIMONIALS ================= -->
  <section class="bg-gray-50 py-10">
    <div class="max-w-7xl mx-auto px-4">
      <!-- Carousel -->
      <div class="relative overflow-hidden px-16 md:px-0">
        <!-- Track -->
        <div
          class="flex transition-transform duration-500 ease-in-out"
          :style="trackStyle"
        >
          <!-- Slide -->
          <div
            v-for="(t, i) in testimonials"
            :key="i"
            class="min-w-full flex justify-center"
          >
            <!-- Card -->
            <div
              class="bg-white border border-gray-200 rounded-xl p-8 max-w-xl shadow-sm"
            >
              <div class="flex gap-2 mb-4">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  fill="#FFD700"
                  class="size-6"
                >
                  <path
                    fill-rule="evenodd"
                    d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.006 5.404.434c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.434 2.082-5.005Z"
                    clip-rule="evenodd"
                  />
                </svg>

                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  fill="#FFD700"
                  class="size-6"
                >
                  <path
                    fill-rule="evenodd"
                    d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.006 5.404.434c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.434 2.082-5.005Z"
                    clip-rule="evenodd"
                  />
                </svg>

                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  fill="#FFD700"
                  class="size-6"
                >
                  <path
                    fill-rule="evenodd"
                    d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.006 5.404.434c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.434 2.082-5.005Z"
                    clip-rule="evenodd"
                  />
                </svg>

                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  fill="#FFD700"
                  class="size-6"
                >
                  <path
                    fill-rule="evenodd"
                    d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.006 5.404.434c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.434 2.082-5.005Z"
                    clip-rule="evenodd"
                  />
                </svg>

                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  fill="#FFD700"
                  class="size-6"
                >
                  <path
                    fill-rule="evenodd"
                    d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.006 5.404.434c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.434 2.082-5.005Z"
                    clip-rule="evenodd"
                  />
                </svg>
              </div>
              <p class="text-gray-600 font-light text-2xl leading-relaxed">
                "{{ t.text }}"
              </p>

              <div class="flex items-center gap-4 mt-6">
                <img
                  :src="t.image"
                  :alt="t.name"
                  class="w-12 h-12 rounded-full object-cover"
                />
                <div>
                  <p class="font-medium text-gray-900">{{ t.name }}</p>
                  <p class="text-sm text-gray-500">{{ t.role }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Controls -->
        <button
          @click="prev"
          class="absolute left-0 md:left-4 top-1/2 -translate-y-1/2 bg-white hover:bg-gray-50 border border-gray-200 rounded-full w-12 h-12 shadow-md hover:shadow-lg transition-all duration-200 flex items-center justify-center text-gray-700 hover:text-gray-900 text-2xl font-light"
        >
          ←
        </button>

        <button
          @click="next"
          class="absolute right-0 md:right-4 top-1/2 -translate-y-1/2 bg-white hover:bg-gray-50 border border-gray-200 rounded-full w-12 h-12 shadow-md hover:shadow-lg transition-all duration-200 flex items-center justify-center text-gray-700 hover:text-gray-900 text-2xl font-light"
        >
          →
        </button>
      </div>

      <!-- Dots -->
      <div class="flex justify-center gap-2 mt-6">
        <button
          v-for="(_, i) in testimonials"
          :key="i"
          class="w-2.5 h-2.5 rounded-full transition-colors"
          :class="index === i ? 'bg-blue-600' : 'bg-gray-300'"
          @click="index = i"
        />
      </div>
    </div>
  </section>
</template>
