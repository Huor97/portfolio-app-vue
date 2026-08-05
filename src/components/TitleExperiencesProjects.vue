<script setup lang="ts">
defineProps<{
  title1: string;
  title2: string;
}>();
</script>

<template>
  <div class="relative">
    <h1 class="max-sm:text-[50px] md:text-[100px] lg:text-[120px] font-[Oswald] tracking-wide font-bold mt-40">
      <span class="text-white p-[0.2em]">{{ title1 }}</span>
      <span class="stroke__projets">{{ title2 }}</span>
    </h1>
  </div>
</template>

<style scoped>
.stroke__projets {
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: #ffffff;
}
</style>
