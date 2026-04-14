<script lang="ts" setup>
interface ContactInfo {
  phoneNumber: string;
  address: string;
}

defineProps<{
  contactInfo: ContactInfo;
}>();

const revealed = reactive({
  label: false,
  number: false,
});

onMounted(() => {
  setTimeout(() => {
    revealed.label = true;
  }, 200);

  setTimeout(() => {
    revealed.number = true;
  }, 400);
});
</script>

<template>
  <div class="py-2 bg-gray-100">
    <div class="container mx-auto px-4">
      <div class="flex flex-col lg:flex-row items-center justify-end gap-4">
        <div
          class="text-gray-800 text-sm lg:text-base whitespace-nowrap"
          :class="{
            revealed: revealed.label,
            unrevealed: !revealed.label,
          }"
        >
          Call Today to Get a Free Estimate
        </div>
        <div
          class="flex items-center gap-2"
          :class="{
            revealed: revealed.number,
            unrevealed: !revealed.number,
          }"
        >
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
          <a
            :href="`tel:${contactInfo.phoneNumber}`"
            class="text-[#3ea8db] hover:text-[#3ea8db] text-lg font-bold transition-colors whitespace-nowrap"
            v-text="contactInfo.phoneNumber"
          />
        </div>
      </div>
    </div>
  </div>
</template>
