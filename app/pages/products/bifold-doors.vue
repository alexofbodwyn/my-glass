<script setup lang="ts">
/* ---------------- Assets ---------------- */
import heroImage from "~/assets/img/products/bifold-doors/01.webp";
import gallery02 from "~/assets/img/products/bifold-doors/02.jpg";
import gallery03 from "~/assets/img/products/bifold-doors/03.jpg";

/* ---------------- Page Content ---------------- */
const pageTitle = "Premium <strong>Aluminium Bifold Doors</strong>";

const pageIntro =
  "Our aluminium bifold doors are designed to open up your home with style and functionality. Perfect for modern extensions, patios, or connecting indoor and outdoor spaces seamlessly, with bifold doors available from <strong>£899</strong>.";

const heroAlt = "Aluminium bifold doors installed in a modern UK home";

const sectionTitle = "Open Your Home with Style & Light";

const paragraphs = [
  "Our aluminium bifold doors feature slim, strong profiles that maximise natural light and provide a seamless connection between indoor and outdoor living spaces.",
  "Engineered for smooth operation and long-lasting performance, these doors offer excellent thermal efficiency, security, and low maintenance for UK homes.",
  "Each bifold door is precision-manufactured and professionally installed to ensure perfect alignment, weather resistance, and a refined finish that enhances your property.",
];

const specsTitle = "Technical Specifications";

const specs = [
  { label: "Thermal Performance", value: "Uw values from 1.3 W/m²K" },
  { label: "Glazing Options", value: "Double or triple glazed, low-E glass" },
  {
    label: "Opening Options",
    value: "Multi-panel folding configuration up to 7 panels",
  },
  { label: "Security", value: "High-security locking system included" },
  { label: "Frame Material", value: "Thermally broken aluminium" },
];

const galleryTitle = "Bifold Door Installations";

const galleryImages = [
  {
    src: gallery02,
    label: "Aluminium bifold doors fully opened to patio – exterior view",
  },
  {
    src: gallery03,
    label: "Interior view showing wide, unobstructed access and natural light",
  },
  {
    src: heroImage,
    label: "Sleek aluminium bifold doors on a modern UK extension",
  },
];

const ctaText =
  "Ready to transform your home with premium aluminium bifold doors?";

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
