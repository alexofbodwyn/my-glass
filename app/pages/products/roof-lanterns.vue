<script setup lang="ts">
/* ---------------- Assets ---------------- */
import heroImage from "~/assets/img/products/roof-lantern/01.png";
import gallery02 from "~/assets/img/products/roof-lantern/02.jpg";
import gallery03 from "~/assets/img/products/roof-lantern/03.jpg";

/* ---------------- Page Content ---------------- */
const pageTitle = "Premium <strong>Roof Lanterns</strong>";

const pageIntro =
  "Our aluminium roof lanterns are designed specifically for UK homes, delivering maximum natural light, excellent thermal performance, and a clean architectural finish. Ideal for flat roof extensions, kitchens, and living spaces, with roof lanterns available from <strong>£500</strong>.";

const heroAlt = "Aluminium roof lantern installed on a UK flat roof extension";

const sectionTitle = "Designed for UK Homes & Extensions";

const paragraphs = [
  "Our roof lanterns are engineered to meet and exceed UK Building Regulations, offering outstanding thermal efficiency and weather resistance suitable for the British climate.",
  "Slim aluminium profiles allow more daylight to flood into your space while maintaining excellent strength and durability, making them perfect for modern extensions and renovations.",
  "Each roof lantern is precision-manufactured and professionally installed to ensure long-term performance, minimal maintenance, and a refined finish that enhances your home.",
];

const specsTitle = "Technical Specifications";

const specs = [
  { label: "Thermal Performance", value: "Uw values from 0.66 W/m²K" },
  { label: "Glazing Options", value: "Double or triple glazed, low-E glass" },
  { label: "Building Regulations", value: "Compliant with UK Building Regs" },
  { label: "Weather Resistance", value: "Designed for UK wind & rain loads" },
  { label: "Frame Material", value: "Thermally broken aluminium" },
];

const galleryTitle = "Roof Lantern Installations";

const galleryImages = [
  {
    src: gallery02,
    label: "Roof lantern fitted to rear extension – exterior view",
  },
  {
    src: gallery03,
    label: "Internal view showing increased daylight and clean lines",
  },
  {
    src: heroImage,
    label: "Slim-profile aluminium roof lantern on flat roof",
  },
];

const ctaText =
  "Looking to add more natural light to your extension with a premium roof lantern?";

const ctaHref = "/contact";
</script>

<template>
  <ProductInfo
    :page-title="pageTitle"
    :page-intro="pageIntro"
    :hero-image="heroImage"
    :hero-alt="heroAlt"
    :section-title="sectionTitle"
    :paragraphs="paragraphs"
    :specs-title="specsTitle"
    :specs="specs"
    :gallery-title="galleryTitle"
    :gallery-images="galleryImages"
    :cta-text="ctaText"
    :cta-href="ctaHref"
  />
</template>
