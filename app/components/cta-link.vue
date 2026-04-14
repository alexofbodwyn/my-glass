<script lang="ts" setup>
defineProps({
  href: {
    type: String,
    required: true,
  },
});
</script>
<template>
  <a
    :href="href"
    class="uppercase tracking-wide text-white inline-block bg-[#3ea8db] hover:bg-[#3ea8db]/90 transition-colors py-2 px-8 rounded-full shadow-lg whitespace-nowrap text-sm lg:text-base"
  >
    <slot></slot>
  </a>
</template>
