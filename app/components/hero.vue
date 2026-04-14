<script setup lang="ts">
import { reactive, onMounted } from "vue";

const revealed = reactive({
  image: false,
  title: false,
  subtitle: false,
  button: false,
});

onMounted(() => {
  const previousSectionDelay = 200;

  // background image first
  setTimeout(() => {
    revealed.image = true;
  }, previousSectionDelay + 100);

  // title
  setTimeout(() => {
    revealed.title = true;
  }, previousSectionDelay + 300);

  // subtitle
  setTimeout(() => {
    revealed.subtitle = true;
  }, previousSectionDelay + 500);

  // CTA
  setTimeout(() => {
    revealed.button = true;
  }, previousSectionDelay + 700);
});
</script>

<template>
  <div class="relative mt-[80px] min-h-[75vh] flex flex-col justify-center">
    <div class="absolute inset-0">
      <img
        :class="{
          revealed: revealed.image,
          unrevealed: !revealed.image,
        }"
        src="~/assets/img/pexels-photo-5691503.jpeg"
        class="w-full h-full object-cover"
      />
    </div>

    <div class="absolute inset-0 bg-black/70"></div>

    <div class="relative">
      <h1
        class="text-gray-100 text-center text-4xl font-light lg:text-6xl mb-4 tracking-wider leading-normal"
        :class="{
          revealed: revealed.title,
          unrevealed: !revealed.title,
        }"
      >
        Premium Aluminium<br /><strong>Doors & Windows</strong>
      </h1>
      <p
        class="text-center text-gray-400 mb-8 text-base lg:text-xl mx-10 lg:mx-0 font-base tracking-wide"
        :class="{
          revealed: revealed.subtitle,
          unrevealed: !revealed.subtitle,
        }"
      >
        Expertly crafted aluminium doors and windows,<br />
        available supply-only or fully installed, built to elevate your space —
        bespoke orders £POA.
      </p>
      <div class="flex justify-center">
        <cta-link
          :class="{
            revealed: revealed.button,
            unrevealed: !revealed.button,
          }"
          href="/contact"
          >Schedule My Appointment</cta-link
        >
      </div>
    </div>
  </div>
</template>
