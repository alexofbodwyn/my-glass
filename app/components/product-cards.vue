<script setup lang="ts">
/* ---------------- Assets ---------------- */
import roofLantern from "~/assets/img/products/roof-lantern/01.png";
import bifoldDoor from "~/assets/img/products/bifold-doors/01.webp";
import aluDoor from "~/assets/img/products/aluminum-doors/01.jpg";
import aluWindow from "~/assets/img/products/aluminum-windows/01.jpeg";
import pvcWindow from "~/assets/img/products/pvc-windows/01.jpg";
import compositeDoor from "~/assets/img/products/composite-doors/01.jpg";

/* ---------------- Product List ---------------- */
interface Product {
  title: string;
  description: string;
  image: string;
  ctaHref: string;
  ctaLabel: string;
}

const products: Product[] = [
  {
    title: "Roof Lanterns",
    description:
      "Elegant aluminium roof lanterns designed to flood your extension with natural light.",
    image: roofLantern,
    ctaHref: "/products/roof-lanterns",
    ctaLabel: "Learn more",
  },
  {
    title: "Aluminium Bifold Doors",
    description:
      "Slimline bifold doors that open up your home with light, space, and flexibility.",
    image: bifoldDoor,
    ctaHref: "/products/bifold-doors",
    ctaLabel: "Learn more",
  },
  {
    title: "Bespoke Aluminium Doors",
    description:
      "Made-to-measure aluminium doors crafted to your exact size, style, and finish.",
    image: aluDoor,
    ctaHref: "/products/aluminum-doors",
    ctaLabel: "Learn more",
  },
  {
    title: "Aluminium Windows",
    description:
      "Modern aluminium windows offering strength, thermal efficiency, and clean lines.",
    image: aluWindow,
    ctaHref: "/products/aluminum-windows",
    ctaLabel: "Learn more",
  },
  {
    title: "PVC Windows",
    description:
      "Affordable, low-maintenance PVC windows ideal for replacements or new builds.",
    image: pvcWindow,
    ctaHref: "/products/pvc-windows",
    ctaLabel: "Learn more",
  },
  {
    title: "Composite Doors",
    description:
      "Secure and stylish composite doors designed to enhance any home entrance.",
    image: compositeDoor,
    ctaHref: "/products/composite-doors",
    ctaLabel: "Learn more",
  },
];
</script>

<template>
  <section class="bg-white">
    <!-- Header -->
    <div class="container mx-auto px-4 pt-24 pb-16">
      <div class="max-w-3xl">
        <div
          class="text-lg uppercase tracking-widest text-[#3ea8db] font-medium mb-2"
        >
          Featured Products
        </div>
        <h2 class="text-4xl md:text-5xl font-light text-gray-900 leading-tight">
          Premium Windows & Door Solutions
        </h2>
        <p class="mt-4 text-gray-600 text-base leading-relaxed">
          Explore our carefully selected range of aluminium and glazing
          products, designed for durability, performance, and modern living.
        </p>
      </div>
    </div>

    <!-- Product Grid -->
    <div class="container mx-auto px-4 pb-28">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div
          v-for="product in products"
          :key="product.title"
          class="group relative overflow-hidden rounded-xl shadow-lg bg-black"
        >
          <!-- Image -->
          <img
            :src="product.image"
            :alt="product.title"
            class="w-full h-[320px] object-cover transition-transform duration-700 ease-out group-hover:scale-110"
          />

          <!-- Overlay -->
          <div
            class="absolute inset-0 bg-gradient-to-t from-black/90 via-black/50 to-transparent"
          ></div>

          <!-- Content -->
          <div class="absolute bottom-6 left-6 right-6">
            <h3 class="text-white text-lg font-semibold leading-snug mb-2">
              {{ product.title }}
            </h3>

            <p class="text-gray-200 text-sm leading-relaxed opacity-90 mb-4">
              {{ product.description }}
            </p>

            <cta-link :href="product.ctaHref">
              {{ product.ctaLabel }}
            </cta-link>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
