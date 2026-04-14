<template>
  <!-- ================= WHY CHOOSE US ================= -->
  <section class="bg-white py-24">
    <div
      class="max-w-7xl mx-auto px-4 grid grid-cols-1 lg:grid-cols-2 gap-16 items-center"
    >
      <!-- Left: Content -->
      <div class="max-w-xl">
        <div
          class="text-lg uppercase tracking-widest text-[#3ea8db] font-medium mb-2"
        >
          Why Choose My Glass
        </div>

        <h2 class="text-4xl md:text-5xl font-light text-gray-900 leading-tight">
          Designed Better.<br />Built to Last.
        </h2>

        <p class="mt-6 text-gray-600 leading-relaxed">
          We specialise in premium glazing solutions that combine clean design,
          modern engineering, and flawless installation. From first measurement
          to final fit, every detail is handled with care, precision, and pride
          in our workmanship.
        </p>

        <!-- Checklist -->
        <div class="mt-8 space-y-3">
          <div class="flex items-center gap-3">
            <div
              class="flex-shrink-0 w-5 h-5 bg-[#3ea8db] rounded-full flex items-center justify-center"
            >
              <svg
                class="w-3 h-3 text-white"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="3"
                  d="M5 13l4 4L19 7"
                />
              </svg>
            </div>
            <span class="text-gray-700">
              Bespoke solutions tailored to your space
            </span>
          </div>

          <div class="flex items-center gap-3">
            <div
              class="flex-shrink-0 w-5 h-5 bg-[#3ea8db] rounded-full flex items-center justify-center"
            >
              <svg
                class="w-3 h-3 text-white"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="3"
                  d="M5 13l4 4L19 7"
                />
              </svg>
            </div>
            <span class="text-gray-700">
              Expert installation by certified glaziers
            </span>
          </div>

          <div class="flex items-center gap-3">
            <div
              class="flex-shrink-0 w-5 h-5 bg-[#3ea8db] rounded-full flex items-center justify-center"
            >
              <svg
                class="w-3 h-3 text-white"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="3"
                  d="M5 13l4 4L19 7"
                />
              </svg>
            </div>
            <span class="text-gray-700">
              10-year warranty on all installations
            </span>
          </div>

          <div class="flex items-center gap-3">
            <div
              class="flex-shrink-0 w-5 h-5 bg-[#3ea8db] rounded-full flex items-center justify-center"
            >
              <svg
                class="w-3 h-3 text-white"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="3"
                  d="M5 13l4 4L19 7"
                />
              </svg>
            </div>
            <span class="text-gray-700">
              Energy-efficient, sustainable materials
            </span>
          </div>
        </div>
      </div>

      <!-- Right: Image -->
      <div class="relative">
        <img
          src="https://images.unsplash.com/photo-1600566753086-00f18fb6b3ea?q=80&w=1600&auto=format&fit=crop"
          alt="Premium glazing installation"
          class="w-full h-[420px] object-cover rounded-2xl shadow-lg"
        />
      </div>
    </div>
  </section>

  <!-- ================= TESTIMONIALS ================= -->
  <testimonials />
</template>
