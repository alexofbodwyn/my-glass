<script setup lang="ts">
/* ---------------- Assets ---------------- */
import heroImage from "~/assets/img/products/pvc-windows/01.jpg";
import gallery02 from "~/assets/img/products/pvc-windows/02.jpg";
import gallery03 from "~/assets/img/products/pvc-windows/03.jpg";

/* ---------------- Page Content ---------------- */
const pageTitle = "Premium <strong>PVC Windows</strong>";

const pageIntro =
  "Our PVC windows offer an affordable, durable, and energy-efficient solution for UK homes. Designed to combine low maintenance with long-lasting performance, they are ideal for replacements or new builds, with PVC windows available from as little as <strong>£100</strong>.";

const heroAlt = "PVC windows installed on a modern UK home";

const sectionTitle = "Durable, Low Maintenance, and Energy Efficient";

const paragraphs = [
  "PVC windows are engineered for excellent thermal efficiency, keeping homes warm and helping reduce energy bills while meeting UK Building Regulations.",
  "Available in a wide range of styles and colours, these windows can complement both traditional and modern home designs.",
  "Each window is professionally installed to ensure a secure fit, smooth operation, and a finish that enhances your property’s aesthetics and longevity.",
];

const specsTitle = "Technical Specifications";

const specs = [
  { label: "Thermal Performance", value: "Uw values from 1.6 W/m²K" },
  { label: "Glazing Options", value: "Double or triple glazed, low-E glass" },
  { label: "Material", value: "High-quality PVCu frames" },
  { label: "Maintenance", value: "Virtually maintenance-free" },
  {
    label: "Building Regulations",
    value: "Fully compliant with UK Building Regs",
  },
];

const galleryTitle = "PVC Window Installations";

const galleryImages = [
  {
    src: gallery02,
    label: "PVC windows installed on a UK residential property – exterior view",
  },
  {
    src: gallery03,
    label: "Interior view showing natural light and clean design",
  },
  {
    src: heroImage,
    label: "Modern PVC windows enhancing the home façade",
  },
];

const ctaText =
  "Upgrade your home with affordable, energy-efficient PVC windows today!";

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
