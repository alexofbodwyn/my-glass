<script lang="ts" setup>
import { ref, reactive, onMounted } from "vue";

interface ContactInfo {
  phoneNumber: string;
  address: string;
}

interface NavItem {
  label: string;
  to: string;
  isButton?: boolean;
  children?: { label: string; to: string }[];
}

const contactInfo: ContactInfo = {
  phoneNumber: "+44 7510 429380",
  address: "123 Address Road, Liverpool",
};

const navItems: NavItem[] = [
  { label: "Home", to: "/" },
  {
    label: "Products",
    to: "#",
    children: [
      { label: "Aluminum Windows", to: "/products/aluminum-windows" },
      { label: "Aluminum Doors", to: "/products/aluminum-doors" },
      { label: "Bifold Doors", to: "/products/bifold-doors" },
      { label: "Composite Doors", to: "/products/composite-doors" },
      { label: "PVC Windows", to: "/products/pvc-windows" },
      { label: "Roof Lanterns", to: "/products/roof-lanterns" },
    ],
  },
  { label: "About Us", to: "/about" },
  { label: "Gallery", to: "/gallery" },
  { label: "Reviews", to: "/reviews" },
  { label: "Contact", to: "/contact" },
];

const isOpen = ref(false);

const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};

const revealed = reactive({
  logo: false,
});

onMounted(() => {
  const previousSectionDelay = 400;
  setTimeout(() => {
    revealed.logo = true;
  }, previousSectionDelay + 200);
});
</script>

<template>
  <div>
    <nav class="z-60 shadow-lg bg-white fixed w-full top-0 left-0">
      <TopBar :contact-info="contactInfo" />
      <div class="container mx-auto px-4">
        <!-- Main nav -->
        <div class="flex justify-between items-center py-4 relative z-50">
          <!-- Logo -->
          <div class="flex items-center">
            <a href="/">
              <img
                class="w-[100px] md:w-[140px]"
                src="~/assets/img/logo.png"
                alt="Logo"
                :class="{
                  revealed: revealed.logo,
                  unrevealed: !revealed.logo,
                }"
              />
            </a>
          </div>
          <DesktopMenu :items="navItems" />
          <!-- Hamburger menu button -->
          <button
            @click="toggleMenu"
            class="lg:hidden w-10 h-10 flex flex-col justify-center items-center gap-2 relative z-50"
            aria-label="Toggle menu"
          >
            <span
              :class="[
                'w-7 h-0.5 bg-gray-800 transition-all duration-300 ease-in-out',
                isOpen ? 'rotate-45 translate-y-[5px]' : '',
              ]"
            ></span>
            <span
              :class="[
                'w-7 h-0.5 bg-gray-800 transition-all duration-300 ease-in-out',
                isOpen ? '-rotate-45 -translate-y-[5px]' : '',
              ]"
            ></span>
          </button>
        </div>
        <MobileMenu
          :is-open="isOpen"
          :items="navItems"
          :contact-info="contactInfo"
          @close="toggleMenu"
        />
      </div>
    </nav>
    <!-- Page content slot -->
    <slot />
    <footer-section />
  </div>
</template>
