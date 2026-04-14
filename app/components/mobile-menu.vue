<script lang="ts" setup>
import { ref } from "vue";

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

interface Props {
  isOpen: boolean;
  contactInfo: ContactInfo;
  items?: NavItem[];
}

withDefaults(defineProps<Props>(), {
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
    { label: "Contact", to: "/contact" },
  ],
});

const emit = defineEmits<{
  close: [];
}>();

const openDropdown = ref<number | null>(null);

const toggleDropdown = (index: number) => {
  openDropdown.value = openDropdown.value === index ? null : index;
};
</script>

<template>
  <div
    :class="[
      'lg:hidden fixed inset-0 bg-white overflow-y-auto transition-transform duration-300 ease-in-out',
      isOpen ? 'translate-x-0' : 'translate-x-full',
    ]"
  >
    <div class="container mx-auto px-4 pt-40">
      <ul class="font-medium uppercase flex flex-col gap-6">
        <li v-for="(item, index) in items" :key="index">
          <!-- Item with dropdown -->
          <template v-if="item.children">
            <button
              @click="toggleDropdown(index)"
              class="w-full flex items-center justify-between py-3 text-xl hover:text-[#3ea8db] transition-colors text-left uppercase"
              :class="{ 'text-[#3ea8db]': openDropdown === index }"
            >
              <span>{{ item.label }}</span>
              <svg
                class="w-5 h-5 transition-transform duration-200"
                :class="{ 'rotate-180': openDropdown === index }"
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

            <!-- Dropdown submenu -->
            <Transition
              enter-active-class="transition-all duration-300 ease-out"
              enter-from-class="opacity-0 max-h-0"
              enter-to-class="opacity-100 max-h-96"
              leave-active-class="transition-all duration-200 ease-in"
              leave-from-class="opacity-100 max-h-96"
              leave-to-class="opacity-0 max-h-0"
            >
              <ul v-if="openDropdown === index" class="overflow-hidden">
                <li
                  v-for="(child, childIndex) in item.children"
                  :key="childIndex"
                  class="pl-6 border-l-2 border-gray-200"
                >
                  <NuxtLink
                    :to="child.to"
                    class="block py-2 text-lg normal-case hover:text-[#3ea8db] transition-colors"
                    active-class="text-[#3ea8db]"
                    @click="emit('close')"
                  >
                    {{ child.label }}
                  </NuxtLink>
                </li>
              </ul>
            </Transition>
          </template>

          <!-- Regular link -->
          <NuxtLink
            v-else
            :to="item.to"
            class="block py-3 text-xl hover:text-[#3ea8db] transition-colors"
            :class="index === 0 ? 'font-normal leading-wide' : ''"
            active-class="text-[#3ea8db]"
            :exact-active-class="index === 0 ? 'text-[#3ea8db]' : undefined"
            @click="emit('close')"
          >
            {{ item.label }}
          </NuxtLink>
        </li>
      </ul>

      <!-- Mobile contact info -->
      <div class="mt-8 pt-8 border-t border-gray-200">
        <div class="flex items-center gap-2">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-5 h-5 text-[#3ea8db]"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 0 0 2.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 0 1-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 0 0-1.091-.852H4.5A2.25 2.25 0 0 0 2.25 4.5v2.25Z"
            />
          </svg>
          <NuxtLink
            :href="`tel:${contactInfo.phoneNumber}`"
            class="text-[#3ea8db] hover:text-[#3ea8db] transition-colors text-lg font-bold"
          >
            {{ contactInfo.phoneNumber }}
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>
