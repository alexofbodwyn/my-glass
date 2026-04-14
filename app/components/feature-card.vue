<script lang="ts" setup>
defineProps<{
  title: string;
  description: string;
}>();
</script>

<template>
  <div class="bg-white shadow-2xl py-6 px-8 flex items-center flex-col">
    <slot name="icon"></slot>
    <h3 class="text-lg lg:text-base uppercase font-medium text-center mb-1">
      {{ title }}
    </h3>
    <p class="text-xs lg:text-sm text-center">
      {{ description }}
    </p>
  </div>
</template>
