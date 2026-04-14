<script setup lang="ts">
import { reactive, onMounted, ref } from "vue";

interface NavItem {
  label: string;
  to: string;
  isButton?: boolean;
  children?: { label: string; to: string }[];
}

interface Props {
  items?: NavItem[];
  initialDelay?: number;
  staggerDelay?: number;
}

const props = withDefaults(defineProps<Props>(), {
  items: () => [
    { label: "Home", to: "/" },
    {
      label: "Products",
      to: "#",
      children: [
        { label: "Product 1", to: "/products/product-1" },
        { label: "Product 2", to: "/products/product-2" },
        { label: "Product 3", to: "/products/product-3" },
      ],
    },
    { label: "About Us", to: "/about" },
    { label: "Gallery", to: "/gallery" },
    { label: "Reviews", to: "/reviews" },
    { label: "Contact Us", to: "/contact", isButton: true },
  ],
  initialDelay: 600,
  staggerDelay: 100,
});

const revealed = reactive<Record<string, boolean>>({});
const activeDropdown = ref<number | null>(null);

onMounted(() => {
  props.items.forEach((_, index) => {
    revealed[`item${index}`] = false;
    setTimeout(
      () => {
        revealed[`item${index}`] = true;
      },
      props.initialDelay + (index + 1) * props.staggerDelay,
    );
  });
});

const toggleDropdown = (index: number) => {
  activeDropdown.value = activeDropdown.value === index ? null : index;
};

const closeDropdown = () => {
  activeDropdown.value = null;
};
</script>

<template>
  <div class="hidden lg:block">
    <ul class="font-medium uppercase flex items-center gap-6 xl:gap-8">
      <li
        v-for="(item, index) in items"
        :key="index"
        :class="{
          revealed: revealed[`item${index}`],
          unrevealed: !revealed[`item${index}`],
          relative: item.children,
        }"
      >
        <!-- Wrapper div that includes both trigger and dropdown -->
        <div
          v-if="item.children"
          @mouseenter="activeDropdown = index"
          @mouseleave="closeDropdown()"
        >
          <button
            @click="toggleDropdown(index)"
            class="hover:text-[#3ea8db] transition-colors flex items-center gap-1 uppercase"
            :class="{ 'text-[#3ea8db]': activeDropdown === index }"
          >
            {{ item.label }}
            <svg
              class="w-4 h-4 transition-transform"
              :class="{ 'rotate-180': activeDropdown === index }"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M19 9l-7 7-7-7"
              />
            </svg>
          </button>

          <Transition
            enter-active-class="transition ease-out duration-200"
            enter-from-class="opacity-0 translate-y-1"
            enter-to-class="opacity-100 translate-y-0"
            leave-active-class="transition ease-in duration-150"
            leave-from-class="opacity-100 translate-y-0"
            leave-to-class="opacity-0 translate-y-1"
          >
            <ul
              v-if="activeDropdown === index"
              class="absolute top-full left-0 pt-2 z-50"
            >
              <div class="w-48 bg-white shadow-lg rounded-md py-2">
                <li
                  v-for="(child, childIndex) in item.children"
                  :key="childIndex"
                >
                  <NuxtLink
                    :to="child.to"
                    class="block px-4 py-2 hover:bg-gray-100 hover:text-[#3ea8db] transition-colors normal-case"
                    active-class="text-[#3ea8db] bg-gray-50"
                  >
                    {{ child.label }}
                  </NuxtLink>
                </li>
              </div>
            </ul>
          </Transition>
        </div>

        <cta-link v-else-if="item.isButton" :href="item.to">
          {{ item.label }}
        </cta-link>

        <NuxtLink
          v-else
          :to="item.to"
          class="hover:text-[#3ea8db] transition-colors"
          :class="index === 0 ? 'font-normal leading-wide' : ''"
          active-class="text-[#3ea8db]"
          :exact-active-class="index === 0 ? 'text-[#3ea8db]' : undefined"
        >
          {{ item.label }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>
