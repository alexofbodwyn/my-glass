<script lang="ts" setup>
import { reactive, onMounted } from "vue";

const revealed = reactive<boolean[]>([false, false, false]);

onMounted(() => {
  const previousSectionDelay = 500;

  revealed.forEach((_, index) => {
    setTimeout(
      () => {
        revealed[index] = true;
      },
      previousSectionDelay + 100 + index * 100,
    ); // 200ms stagger
  });
});
</script>

<template>
  <div
    class="-mt-16 relative z-20 grid grid-cols-1 lg:grid-cols-3 gap-6 mx-6 lg:mx-40 xl:mx-60 2xl:mx-80"
  >
    <FeatureCard
      title="Durable & Premium"
      description="High-quality aluminium doors and windows built to last for decades"
      :class="{
        revealed: revealed[0],
        unrevealed: !revealed[0],
      }"
    >
      <template #icon>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          class="size-14"
          fill="none"
          stroke="#3ea8db"
          stroke-width="1.5"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M9 12.75 11.25 15 15 9.75m-3-7.036A11.959 11.959 0 0 1 3.598 6 11.99 11.99 0 0 0 3 9.749c0 5.592 3.824 10.29 9 11.623 5.176-1.332 9-6.03 9-11.622 0-1.31-.21-2.571-.598-3.751h-.152c-3.196 0-6.1-1.248-8.25-3.285Z"
          />
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M12 2.714a9.5 9.5 0 0 0-7.847 4.19 9.517 9.517 0 0 1-.555 2.845C3.214 11.175 3 12.45 3 13.75c0 4.726 3.236 8.705 7.605 9.79.555.138 1.13.208 1.71.208h.185c.58 0 1.155-.07 1.71-.208C18.764 22.455 22 18.476 22 13.75c0-1.3-.214-2.575-.598-3.75a9.517 9.517 0 0 1-.555-2.846A9.5 9.5 0 0 0 12 2.714Z"
            opacity="0.2"
          />
        </svg>
      </template>
    </FeatureCard>

    <FeatureCard
      title="Natural Light & Style"
      description="Roof lanterns designed to brighten your home with elegance"
      :class="{
        revealed: revealed[1],
        unrevealed: !revealed[1],
      }"
    >
      <template #icon>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          class="size-14"
          fill="none"
          stroke="#3ea8db"
          stroke-width="1.5"
        >
          <circle cx="12" cy="12" r="4" fill="#3ea8db" opacity="0.2" />
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M12 2v2m0 16v2M4.93 4.93l1.41 1.41m11.32 11.32 1.41 1.41M2 12h2m16 0h2M4.93 19.07l1.41-1.41m11.32-11.32 1.41-1.41"
          />
          <circle cx="12" cy="12" r="5" stroke-width="1.5" />
        </svg>
      </template>
    </FeatureCard>

    <FeatureCard
      title="Customised Designs"
      description="Bespoke solutions tailored to your space, style, and needs"
      :class="{
        revealed: revealed[2],
        unrevealed: !revealed[2],
      }"
    >
      <template #icon>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          class="size-14"
          fill="none"
          stroke="#3ea8db"
          stroke-width="1.5"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M15.75 15.75 19.5 12l-3.75-3.75m0 0L12 4.5 8.25 8.25M15.75 8.25 12 12m0 0-3.75 3.75M12 12l-7.5 7.5"
            opacity="0.2"
          />
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M9.594 3.94c.09-.542.56-.94 1.11-.94h2.593c.55 0 1.02.398 1.11.94l.213 1.281c.063.374.313.686.645.87.074.04.147.083.22.127.324.196.72.257 1.075.124l1.217-.456a1.125 1.125 0 0 1 1.37.49l1.296 2.247a1.125 1.125 0 0 1-.26 1.431l-1.003.827c-.293.241-.438.613-.43.992a7.723 7.723 0 0 1 0 .255c-.008.378.137.75.43.991l1.004.827c.424.35.534.955.26 1.43l-1.298 2.247a1.125 1.125 0 0 1-1.369.491l-1.217-.456c-.355-.133-.75-.072-1.076.124a6.47 6.47 0 0 1-.22.128c-.331.183-.581.495-.644.869l-.213 1.281c-.09.543-.56.94-1.11.94h-2.594c-.55 0-1.019-.398-1.11-.94l-.213-1.281c-.062-.374-.312-.686-.644-.87a6.52 6.52 0 0 1-.22-.127c-.325-.196-.72-.257-1.076-.124l-1.217.456a1.125 1.125 0 0 1-1.369-.49l-1.297-2.247a1.125 1.125 0 0 1 .26-1.431l1.004-.827c.292-.24.437-.613.43-.991a6.932 6.932 0 0 1 0-.255c.007-.38-.138-.751-.43-.992l-1.004-.827a1.125 1.125 0 0 1-.26-1.43l1.297-2.247a1.125 1.125 0 0 1 1.37-.491l1.216.456c.356.133.751.072 1.076-.124.072-.044.146-.086.22-.128.332-.183.582-.495.644-.869l.214-1.28Z"
          />
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"
          />
        </svg>
      </template>
    </FeatureCard>
  </div>
</template>
