<script setup lang="ts">
/* ---------------- Assets ---------------- */
import heroImage from "~/assets/img/products/composite-doors/01.jpg";
import gallery02 from "~/assets/img/products/composite-doors/02.jpg";
import gallery03 from "~/assets/img/products/composite-doors/03.webp";

/* ---------------- Page Content ---------------- */
const pageTitle = "Premium <strong>Composite Doors</strong>";

const pageIntro =
  "Our composite doors combine style, security, and durability for the perfect front entrance. Designed to enhance the look of any UK home while providing excellent thermal performance and low maintenance, with composite doors available from <strong>£799</strong>.";

const heroAlt = "Modern aluminium composite front door installed on a UK home";

const sectionTitle = "Stylish, Secure, and Energy Efficient";

const paragraphs = [
  "Our composite doors are engineered for superior strength and long-lasting performance, providing excellent security and resistance to weather, warping, and wear.",
  "Available in a wide range of colours, finishes, and panel designs, these doors allow you to create a statement entrance tailored to your home’s style.",
  "Professionally installed, each door ensures optimal thermal efficiency, minimal maintenance, and a polished finish that enhances curb appeal.",
];

const specsTitle = "Technical Specifications";

const specs = [
  { label: "Thermal Performance", value: "Uw values from 1.4 W/m²K" },
  {
    label: "Security",
    value: "Multi-point locking system and reinforced frame",
  },
  { label: "Material", value: "GRP composite with insulated core" },
  {
    label: "Weather Resistance",
    value: "Designed for UK climate and wind loads",
  },
  {
    label: "Customisation",
    value: "Available in multiple colours and finishes",
  },
];

const galleryTitle = "Composite Door Installations";

const galleryImages = [
  {
    src: gallery02,
    label: "Composite front door installed – exterior view",
  },
  {
    src: gallery03,
    label: "Close-up showing elegant design and secure hardware",
  },
  {
    src: heroImage,
    label: "Stylish composite door enhancing the property entrance",
  },
];

const ctaText =
  "Upgrade your home entrance with a premium composite door today!";

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
