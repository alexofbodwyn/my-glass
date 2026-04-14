<script setup lang="ts">
/* ---------------- Assets ---------------- */
import heroImage from "~/assets/img/products/aluminum-windows/01.jpeg";
import gallery02 from "~/assets/img/products/aluminum-windows/02.jpg";
import gallery03 from "~/assets/img/products/aluminum-windows/03.jpg";

/* ---------------- Page Content ---------------- */
const pageTitle = "Premium <strong>Aluminium Windows</strong>";

const pageIntro =
  "Our aluminium windows are designed for modern UK homes, combining sleek aesthetics, superior thermal performance, and long-lasting durability. Ideal for new builds, extensions, or replacement windows, with aluminium windows available from <strong>£250</strong>.";

const heroAlt = "Aluminium windows installed on a modern UK home";

const sectionTitle = "Modern, Durable, and Energy Efficient";

const paragraphs = [
  "Our aluminium windows are engineered to exceed UK Building Regulations, offering excellent thermal efficiency and weather resistance suitable for the British climate.",
  "Slim, strong profiles maximise daylight while providing security and minimal maintenance, perfect for both contemporary and traditional home designs.",
  "Each window is precision-manufactured and professionally installed to ensure long-term performance, energy savings, and a refined finish that enhances your home.",
];

const specsTitle = "Technical Specifications";

const specs = [
  { label: "Thermal Performance", value: "Uw values from 1.2 W/m²K" },
  { label: "Glazing Options", value: "Double or triple glazed, low-E glass" },
  {
    label: "Building Regulations",
    value: "Fully compliant with UK Building Regs",
  },
  { label: "Weather Resistance", value: "Designed for UK wind & rain loads" },
  { label: "Frame Material", value: "Thermally broken aluminium" },
];

const galleryTitle = "Aluminium Window Installations";

const galleryImages = [
  {
    src: gallery02,
    label: "Aluminium window fitted in a modern home – exterior view",
  },
  {
    src: gallery03,
    label: "Interior view showing natural light and slim frames",
  },
  {
    src: heroImage,
    label: "Sleek aluminium windows on a UK residential property",
  },
];

const ctaText = "Looking to upgrade your home with premium aluminium windows?";

const ctaHref = "/contact";
</script>

<template>
  <product-info
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
