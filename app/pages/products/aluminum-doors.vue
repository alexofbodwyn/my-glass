<script setup lang="ts">
/* ---------------- Assets ---------------- */
import heroImage from "~/assets/img/products/aluminum-doors/01.jpg";
import gallery02 from "~/assets/img/products/aluminum-doors/02.jpg";
import gallery03 from "~/assets/img/products/aluminum-doors/03.jpeg";

/* ---------------- Page Content ---------------- */
const pageTitle = "Premium <strong>Bespoke Aluminium Doors</strong>";

const pageIntro =
  "Our bespoke aluminium doors are precision-crafted to suit your exact requirements, combining modern design, strength, and exceptional thermal performance. Ideal for contemporary homes, extensions, and statement entrances, with bespoke aluminium doors starting from <strong>£999</strong>.";

const heroAlt = "Bespoke aluminium door installed on a modern UK home";

const sectionTitle = "Made to Measure. Designed to Impress.";

const paragraphs = [
  "Our aluminium doors are fully bespoke, manufactured to your exact dimensions and specifications, ensuring a perfect fit for your property.",
  "Slim yet strong aluminium profiles allow for larger glass panels, maximising natural light while delivering excellent security and thermal efficiency.",
  "Available in over 200 RAL colours with a wide choice of glazing and hardware options, each door is professionally installed to achieve a refined, high-end finish.",
];

const specsTitle = "Technical Specifications";

const specs = [
  { label: "Thermal Performance", value: "Uw values from 1.2 W/m²K" },
  { label: "Glazing Options", value: "Double or triple glazed, low-E glass" },
  {
    label: "Customisation",
    value: "Made-to-measure sizes, colours, glazing & hardware",
  },
  { label: "Security", value: "High-security multi-point locking systems" },
  { label: "Frame Material", value: "Thermally broken aluminium" },
];

const galleryTitle = "Bespoke Aluminium Door Installations";

const galleryImages = [
  {
    src: gallery02,
    label:
      "Bespoke aluminium door installed on a modern property – exterior view",
  },
  {
    src: gallery03,
    label: "Interior view showing slim frames and large glazed panels",
  },
  {
    src: heroImage,
    label: "Contemporary bespoke aluminium door with clean architectural lines",
  },
];

const ctaText =
  "Looking to create a statement entrance with bespoke aluminium doors?";

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
